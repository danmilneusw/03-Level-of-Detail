# 03 - Profiling the Build and GPU Usage
## Profiling the Build
In week 1, when we profiled our projects we found the Editor loop was sometimes interfering with our results. Profiling inside the editor is fine for making quick changes, but really we want to profile after building our project. This way we can more accurately profile our game.

1. Still using the project you just made with the monkey in it, press Ctrl+7 to open the profiler.

2. Under Profiler Modules, make sure only CPU Usage and GPU Usage are selected.

3. There's some setup before we build our game. Go to Edit > Project Settings and ensure Graphic Jobs is turned off. Set VSYNC Count to Don't Sync. This might add screen-tearing to your game, but it will remove the framerate cap.

4. Position your camera so that the mesh is at LOD0. Go to File > Build Settings. Tick Development Build to then Enable the Autoconnect Profiler option (see below). Press Build And Run. You must put the build in a folder, I'd recommend making a new folder called Build.

<div align="center">
  <a href="Images\03 - Profiling the Build and GPU Usage\03 - Building.png" target="_blank">
    <img src="Images\03 - Profiling the Build and GPU Usage\03 - Building.png" alt="Build Project" style="height:500px;"/>
  </a>
</div>
<br><br>

5. View the recording in the profiler. Take a screenshot of your results. You should save something like this:

<div align="center">
  <a href="Images\03 - Profiling the Build and GPU Usage\GPU Usage Build LOD0.png" target="_blank">
    <img src="Images\03 - Profiling the Build and GPU Usage\GPU Usage Build LOD0.png" alt="LOD0 Build Profile" style="height:500px;"/>
  </a>
</div>
<br><br>

6. Position your camera so that the mesh is at LOD3. Go to File > Build Settings. Like before, tick Development Build to then Enable the Autoconnect Profiler option. Press Build And Run. View your recording.

<div align="center">
  <a href="Images\03 - Profiling the Build and GPU Usage\GPU Usage Build LOD3.png" target="_blank">
    <img src="Images\03 - Profiling the Build and GPU Usage\GPU Usage Build LOD3.png" alt="LOD03 Build Profile" style="height:500px;"/>
  </a>
</div>
<br><br>

Making comparisons between the two, you should see the GPU usage is less when using LOD3 and there should be fewer DrawCalls also. If this were your assignment, you should now use the comparison tool discussed in week 1.