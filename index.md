---
layout: home
title: "h3r2tic's grimoire"
nonsense:
    - title: "Raytracing in Hybrid Real-Time Rendering"
      description: "A mini-game we developed at SEED for autonomous agents: [PICA PICA](https://www.ea.com/seed/news/seed-project-picapica); the cutest Skynet implementation around.<br/><br/>It sports an unusual renderer: rasterization meets raytracing meets specialized denoising. I worked on global illumination, reflections, shadows, and a bunch more. Here's [some slides](https://www.ea.com/seed/news/seed-dd18-presentation-slides-raytracing) on those."
      banner: picaPica.png
    - title: Hacking GCN via OpenGL
      description: "AMD's Graphics Core Next GPU architecture has a number of interesting features which one cannot access via standard APIs. I show how to hack around the OpenGL driver, and feed it native shaders written in GCN ISA instead of GLSL. [Slides here!](https://onedrive.live.com/view.aspx?resid=EBE7DEDA70D06DA0!107&app=PowerPoint&authkey=!AD-O3oq3Ung7pzk)"
      banner: hackingGcnWithOpengl.png
    - title: A deferred material rendering system
      description: "Practical application of the GCN hacks: indirect dispatch of lots of unique compute shaders and native barycentric coordinate access. Those allows for efficient surface shading in a deferred manner without the use of ubershaders. Geometry and material descriptions can be decoupled, and we gain a lot of control over shading frequency. [Slides here!](https://onedrive.live.com/view.aspx?resid=EBE7DEDA70D06DA0!115&app=PowerPoint&authkey=!AP-pDh4IMUug6vs)"
      banner: deferredMaterialRenderingSystem.png
    - title: How not to use DLLs
      banner: howNotToUseDlls.png
      description: "Runtime loading of *object* files, relocation of DLLs. Mostly harmful stuff. [Article here.](posts/how-not-to-use-dlls/)"
    - title: Stochastic Screen-Space Reflections
      vimeo: 115108688
      description: "Importance sampled screen-space reflections with a novel spatiotemporal filter. I prototyped it in a toy engine written in the Rust language, and later ported to Frostbite. It first shipped in Mirror's Edge and Need for Speed.<br/><br/>
      Check out the slides for my Siggraph 2015 talk which was part of [Advances in Real-Time Rendering in Games](http://advances.realtimerendering.com/s2015/)."
    - title: Frostbite
      description: "I worked in the Frostbite Rendering team in Stockholm for three years. My focus was Image Quality, and included physically-based rendering, tiled lighting, screen-space and planar reflections, skin shading, high dynamic range stuff (grading, display mapping, vendor-specific output), physically-inspired glare, checkerboard rendering, temporal anti-aliasing, motion blur, global illumination, as well as low-level PS4 and XB1 work. I even had some fun with Mantle. My code ended up in franchises like Battlefield, Mass Effect, Battlefront, Need For Speed, FIFA, Mirror's Edge, Plants vs Zombies, and a few others."
      banner: frostbiteEngine.jpg
    - title: "Alien: Isolation"
      banner: alienIsolation.jpg
      description: "I joined Creative Assembly straight out of university, and had the opportunity to work on Alien: Isolation. It was quite a blast, and an amazing learning experience. I contributed to deferred lighting, physically-based rendering, end-to-end skin and hair pipelines and rendering, in-house real-time radiosity, post-processing, and a bunch of other tech.<br/>
      I presented some of [our deferred rendering tricks](https://studylib.net/doc/5611082/develop-2012) at Develop 2012."
    - title: Nucleus
      banner: nucleus.jpg
      description: "An old rendering engine I wrote for my master's thesis. It had a lot of over-engineering and naive design, but also a few neat ideas, and a custom node-based shader editor.<br/>
      [Read more.](http://h3.gd/pub/msc.html)"
    - title: Hybrid
      banner: hybrid.png
      description: "A crossbreed between immediate- and retained-mode graphical user interfaces. Both styles could be used where appropriate, and a domain-specific language helped with the creation of fancy layouts. The backend targeted the GPU directly and rendered in only a handful of draw calls. Written in the 1.0 version of the D programming language.
      [User docs here.](http://h3.gd/code/hybrid/)"
    - title: Authority-based client-server netcode
      vimeo: 89059299
      description: "An excursion into an unusual territory for me -- game networking and physics synchronization. I had the ambition of making a Battlefield-like game, but that turned out to be too vast in scope... Surprise, surprise! In any case, it was a valuable and fun learning experience. I used ENet for the low-level networking, rolled an authority scheme on top of it, and synchronized a Havok physics simulation as well as gameplay logic."
    - title: Compile-time raytracing
      banner: ctrace.png
      description: "Ok, this one is here just for the bragging rights. I claim to have written the world's first compile-time raytracer. That is, the compiler runs, and there's no executable generated. Instead, it prints garbage to *stdout*. Redirect it to a file, and you have an image. I did it in the D language before it even hit the 1.0 version, so it didn't have any of the modern compile-time function evaluation. [Old blurb here.](posts/ctrace/)"
---

![avatar](avatar.jpg){:style="float: right; margin: 1em; width: 128px" class="softShadow"}

# Hello, world!

My name is Tomasz Stachowiak, and I'm a professional madman. I mostly tinker with real-time graphics, and occasionally trace my path in Veach-land. By day I'm a reputable software engineer at [Embark Studios](https://www.embark-studios.com/), while at night I bask in the suffering of compilers and GPUs. Here's some of my nonsense:

{% for item in page.nonsense %}
<h2 style="clear: left; padding-top: 1em">{{item.title}}</h2>
{% if item.banner %}![banner]({{item.banner}}){:style="width: 320px; float: left; margin-right: 1em; margin-bottom: 1em" class="softShadow"}{% else %}<iframe src="https://player.vimeo.com/video/{{item.vimeo}}?autoplay=1&loop=1&title=0&byline=0&portrait=0" width="320" height="200" frameborder="0" style="float: left; margin-right: 1em; margin-bottom: 1em" webkitallowfullscreen mozallowfullscreen allowfullscreen class="softShadow"></iframe>{% endif %}{{item.description}}{% endfor %}
