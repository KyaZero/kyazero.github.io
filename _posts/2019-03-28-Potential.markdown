---
layout: post
title: Potential
img: mockup.jpg
---

Potential is a First-Person Shooter game that our team made in 10 weeks half time.

I personally contributed to this game project on the rendering and vfx side of things, as I primarily worked with artists and technical artists to achieve the look we were going for. ![](../assets/mockup.jpg)
To achieve a similar look to this mockup I had to spend time implementing Screen-Space Reflections and learning how people use it in their games.
This has allowed our artists to match our style greatly and I feel that I've learned a bunch of stuff whilst researching techniques for SSR.


The interesting parts of the shader are as follows:

{% highlight cpp %}
//sample data from g-buffer
float3 position = PositionTexture.Sample(sampler, input.uv).xyz;
float3 normal = NormalTexture.Sample(sampler, input.uv).xyz;

//in my case they were in world space so I convert them to view space...
float3 viewPos = mul(view, float4(position, 1.0)).xyz;
float3 viewNormal = mul(view, float4(normal, 0.0)).xyz;

//reflect vector with pixel normal
float3 reflection = reflect(position, normal);
{% endhighlight %}

I get a view position and view normal and then calculate the reflection vector off of that information.

{% highlight cpp %}
float3 step = reflection;
float3 newPosition = position + step;

for(int i = 0; i < loops; ++i)
{
    //grab new position and convert to post projection space
    float4 vPos = float4(viewPos, 1.0);
    float4 samplePosition = mul(projection, vPos);

    // adjust from NDC to DirectX space..
    samplePosition.xy = (samplePosition.xy / samplePosition.w) * float2(0.5, -0.5) + 0.5;

{% endhighlight %}

Then I calculate the new view position and transform it into post projection space and correct it for DirectX.

{% highlight cpp %}
    float currentDepth = abs(vPos.z);
    //I multiply with far plane because we have our depth stored linearly by using viewPos.z / farPlane
    float sampleDepth = abs(DepthTexture.Sample(sampler, samplePosition.xy).w * farPlane); 

    //if depth is close enough then sample pixel color
    if (abs(samplePosition.z - sampleDepth) < 0.001)
    {
        outputColor = ColorTexture.Sample(sampler, samplePosition.xy).xyz;
    }

    //else keep stepping
    step *= 1.0 - 0.5 * max(sign(currentDepth - sampleDepth), 0.0); //progress the step
    newPosition += step * (sign(sampleDepth - currentDepth) + 0.000001); //set new position and loop again
    outputColor = float3(0,0,0);
}
{% endhighlight %}

Finally we compare depth and return the color *(or if you want, UV)* and keep stepping until we either hit something or just return nothing

That's the gist of the SSR implementation, with some edge fading and such applied in our actual engine but left out for simplicity.

I also wrote a CPU-based particle system from scratch during the later weeks in this project as we felt we needed a more solid particle implementation to allow our artists to get their vision across.