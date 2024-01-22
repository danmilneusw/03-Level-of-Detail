# 02 - The Memory Profiler
Unity comes with a tool specifically for analysing memory usage. Let's take a look at it.

1. Go to Window > Package Manager. Set Packages to Unity Registry. Then find the  Memory Profiler and select Install. 

<div align="center">
  <a href="Images\02 - The Memory Profiler\2 - Install Memory Profiler.png" target="_blank">
    <img src="Images\02 - The Memory Profiler\2 - Install Memory Profiler.png" alt="Install Memory Profiler" style="height:300px;"/>
  </a>
</div>
<br>

Open it at Window > Analysis > Memory Profiler.

2. Run the game and position the camera so that the mesh is at LOD0 and select Capture New Screenshot in the Memory Profiler. Keep the game running.

<div align="center">
  <a href="Images\02 - The Memory Profiler\2 - Memory Snapshot 1.png" target="_blank">
    <img src="Images\02 - The Memory Profiler\2 - Memory Snapshot 1.png" alt="Memory Snapshot 1" style="height:300px;"/>
  </a>
</div>
<br><br>

2. Reposition the camera so that the mesh is at LOD0 and select Capture New Screenshot in the Memory Profiler.

<div align="center">
  <a href="Images\02 - The Memory Profiler\2 - Memory Snapshot 2.png" target="_blank">
    <img src="Images\02 - The Memory Profiler\2 - Memory Snapshot 2.png" alt="Memory Snapshot 1" style="height:300px;"/>
  </a>
</div>
<br><br>

3. Change to Compare Snapshots (top left) and select both of your snapshots. You'll find that the snapshots should be very similar. In fact for me, the second snapshot used slighty more memory even though this was taken when LOD3 was being rendered!

<div align="center">
  <a href="Images\02 - The Memory Profiler\2 - Compare Snapshots.png" target="_blank">
    <img src="Images\02 - The Memory Profiler\2 - Compare Snapshots.png" alt="Memory Snapshot Comparison" style="height:300px;"/>
  </a>
</div>
<br><br>

4. Don't worry, this actually makes sense. I will explain, but first, switch back to Single Snapshot mode and select the second snapshot. Inspect the Top Unity Object Categories. Here you will find all of the LOD meshes have been loaded into the RAM and always are, no matter what mesh is being rendered. Meshes of different LODs need to be loaded quickly. If we are quickly approaching a tree, the highly detailed LOD should ideally be loaded before we notice. If it's not in RAM already, we can't access it quickly and there could be a delay (especially if the end user is using an HDD instead of an SSD or better). 

<div align="center">
  <a href="Images\02 - The Memory Profiler\2 - Memory Storage.png" target="_blank">
    <img src="Images\02 - The Memory Profiler\2 - Memory Storage.png" alt="Memory Storage" style="height:300px;"/>
  </a>
</div>
<br><br>

So what's the point of using DLODs if we use more RAM!? Move onto the next tutorial.