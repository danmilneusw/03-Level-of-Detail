# 03-Level-of-Detail
## Introduction
Level of detail, or LOD, typically refers to the complexity of a 3D model in our scene, often measured by the number of vertices. Meshes with a high level of detail and a high polygon/face count look great up close but when further away having a high performance can hinder performance when we don't need so much detail. But it can be used more generally too; it is any optimisation that dynamically alters the detail of something.

One example of LOD is Nanite, a geometry optimiser, which was introduced in Unreal Engine 5. Nanite works by breaking down meshes into clusters of triangles. Based on factors, like distance from the camera and visibility, LOD is applied dynamically so that only the approriate sections of the mesh are loaded to give the perception to the end-user that the maximum level of detail is being rendered. All this processing is kept on the GPU too, so it is very efficient as no information needs to be passed between the CPU and GPU.

Nanite is quite complex. You can learn more about it in your own time in the video linked below. Today, we'll focus on some of the most commonly LOD optimisation techniques in the game development industry.

[Nanite in UE5: The End of Polycounts? | Unreal Engine](https://youtu.be/xUUSsXswyZM?si=crGMuugWq1hhWah3)

## Summary
- Learn some examples of LOD
- Implement LOD inside Unity
- Learn to use the Unity Memory Profiler

## Discrete Level of Detail (DLOD)
Discrete Level of Detail, or DLOD, is an optimisation technique where various models are created to represent the same object. The highest quality model is typically created first, then variations of lower and lower quality copies are created. Code is implemented to change the model in use based on factors defined by the developer, such as distance from the camera.

<div align="center">
  <a href="Images\Wikipedia Discrete LOD Example.png" target="_blank">
    <img src="Images\Wikipedia Discrete LOD Example.png" alt="Audio Profiler" style="height:200px;"/>
  </a>
</div>
<div align="center">
  <a href="https://en.wikipedia.org/wiki/Level_of_detail_(computer_graphics)">
  source
  </a>
</div>

Take the spheres in the image above, for closeups of the sphere, a higher quality sphere is used and for viewing the object far away, less detail is used. Because the lower quality spheres contain fewer vertices and therefore require less memory, we have more freedom with what we can render to the end-user, like render lots of objects or save memory on low-spec hardware. This technique works well for a range of objects:

<div align="center">
  <a href="Images\Rabbits.gif" target="_blank">
    <img src="Images\Rabbits.gif" alt="Audio Profiler" style="height:200px;"/>
  </a>
</div>
<div align="center">
  <a href="https://cs.nyu.edu/~yap/classes/visual/01f/lect/l4/">
  source
  </a>
</div>
<br>

Spyro the Dragon was one of the first games to implement DLOD, albeit more rudimentary. They used a simple method where close objects were rendered as they normally would be but far away objects were identical but were textureless. <a href="https://web.archive.org/web/20181024024756/https://www.gamestm.co.uk/features/holiday-gift-guide-the-best-of-the-vault-2016/">source</a>


## Distance Fog
Distance Fog is a technique that uses fog to hide nearby culling of objects outside of a short draw-distance. Fog was a staple of many eariler games and was best used when working in collaboration with the gameplay or mood.

>"And who could forget Silent Hill on the PlayStation? Its impenetrable mist was at the center of its horror, an ever-present adversary that seemed to close in and choke the player." [source](https://www.vice.com/en/article/mg9p3a/in-praise-of-video-gamings-old-dalliance-with-distance-fog")
<br>

<div align="center">
  <a href="Images\Silent Hill 2 Screenshot 2.jpg" target="_blank">
    <img src="Images\Silent Hill 2 Screenshot 2.jpg" alt="Audio Profiler" style="height:200px;"/>
  </a>
</div>
<div align="center">
Silent Hill
  <a href="https://pin.it/7FnQaZVen">
  source
  </a>
</div>
<br>

<div align="center">
  <a href="Images\Silent Hill 2 Screenshot.jpg" target="_blank">
    <img src="Images\Silent Hill 2 Screenshot.jpg" alt="Audio Profiler" style="height:200px;"/>
  </a>
</div>
<div align="center">
Silent Hill 2
  <a href="https://whatculture.com/gaming/10-brilliant-ps2-titles-that-give-you-instant-nostalgia?page=2">
  source
  </a>
</div>
<br>

Modding the fog out, Silent Hill 2 actually looks like this!

<div align="center">
  <a href="Images\Silent Hill 2 Screenshot Fog Removed.jpg" target="_blank">
    <img src="Images\Silent Hill 2 Screenshot Fog Removed.jpg" alt="Audio Profiler" style="height:200px;"/>
  </a>
</div>
<div align="center">
Silent Hill 2 without Fog
  <a href="https://www.reddit.com/r/gaming/comments/9z1eh2/this_is_how_the_original_silent_hill_looks/">
  source
  </a>
</div>
<br>

Fog continued to be used in later video games where culling objects completely wasn't mandotory for complex scenes. In these examples, fog is used to hide how models of a low level of detail have been used. This is why fog is common in open-world games.

<div align="center">
  <a href="Images\GTA IV Screenshot.png" target="_blank">
    <img src="Images\GTA IV Screenshot.png" alt="Audio Profiler" style="height:200px;"/>
  </a>
</div>
<div align="center">
GTA IV
  <a href="https://www.reddit.com/r/GTAIV/comments/132gcy5/gta_iv_15year_anniversary_screenshot_compilation/?rdt=51373">
  source
  </a>
</div>
<br>

<div align="center">
  <a href="Images\GTA V Screenshot.png" target="_blank">
    <img src="Images\GTA V Screenshot.png" alt="Audio Profiler" style="height:200px;"/>
  </a>
</div>
<div align="center">
GTA V
  <a href="https://www.gtabase.com/grand-theft-auto-v/screenshots/ps4-xb1-pc-screenshots/">
  source
  </a>
</div>
<br>

More recently, software progress has enabled us to implement near-photorealistic fog. Unlike in previous examples, this fog actually comes at a cost to performance and is used primarily for aesthetics. But, of course, the option to use simpler fog to save computation still exists today.
<br><br>

<div align="center">
  <a href="Images\Fog then Versus Now.png" target="_blank">
    <img src="Images\Fog then Versus Now.png" alt="Wikipedia Discrete LOD Example" style="height:400px;"/>
  </a>
</div>
<div align="center">
  <a href="https://www.reddit.com/r/gaming/comments/mwpahz/fog/">
  source
  </a>
</div>
<br>

## Tutorial
1. Complete the **01 - Discrete LOD Tutorial**. You will learn to make your own discrete LOD system in Unity and learn some Blender too.
2. Complete the **02 - The Memory Profiler** tutorial. You will see how your DLOD implementation affected RAM...
3. Complete the **03 - Profiling the Build and GPU Usage** tutorial. You will see how your DLOD implementation affected GPU usage and learn to profile your build for more accurate performance analysis.
4. Aside from using DLOD, developing a new LOD optimisation system for your assignment will help you gain marks. Think of some new ways to implement LOD that could work for your own project. Come up with your own too, but here's some ideas:
- Detect the speed of an object. If it is moving so fast it is difficult to make out the details of it, then why not implement LOD Groups with lower texture versions that change based on speed?
- We've covered LOD for meshes. What else could be compressed if far from the camera? What about textures? Can you write a script that dynamically compresses them from float to integer? Here is some [info on Unity Texture Formats](https://docs.unity3d.com/Manual/class-TextureImporterOverride.html) and here is some [info on Texture Import Settings](https://docs.unity3d.com/Manual/class-TextureImporter.html.)


## Extra Resources
- [Unreal Engine's Nanite](https://docs.unrealengine.com/5.0/en-US/nanite-virtualized-geometry-in-unreal-engine/)

### Distance Fog
- [Distance Fog Wikipedia Page](https://en.wikipedia.org/wiki/Distance_fog)

### LOD
- [Unity Docs - Memory Profiler](https://docs.unity3d.com/Packages/com.unity.memoryprofiler@1.1/manual/index.html) ⭐
- [Level of Detail (LOD) for meshes](https://docs.unity3d.com/Manual/LevelOfDetail.html#:~:text=The%20LOD%20technique%20allows%20Unity,meshes%20are%20called%20LOD%20levels.)
- [Unity - Working with LODs Tutorial](https://learn.unity.com/tutorial/working-with-lods-2019-3#)
- [Full Monkey LOD Tutorial (Using Out of Data Blender)](https://www.youtube.com/watch?v=ifNyVS2_6f8)
- [A drop-in dynamic resolution script (by Unity)](https://github.com/Unity-Technologies/DynamicResolutionSample)

### Unity Memory Profiler
- [Everything you need to know about Memory Profiler 1.0.0](https://blog.unity.com/engine-platform/everything-you-need-to-know-about-memory-profiler)

- [USING MEMORY PROFILING TOOLS IN UNITY TO ANALYZE MEMORY USAGE](https://unity.com/how-to/analyze-memory-usage-memory-profiling-tools#:~:text=The%20Memory%20Profiler%20package%3A%20This,compare%20usage%20between%20multiple%20snapshots.)
