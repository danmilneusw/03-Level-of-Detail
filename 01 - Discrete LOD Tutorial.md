# 01 - Discrete LOD Tutorial
1. Open a new Unity project and create three identical spheres. Put them as children of a parent group and name them as shown in the below image.

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\Objects.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\Objects.png" alt="Adding Spheres" style="height:200px;"/>
  </a>
</div>
<br><br>

2. Create three new materials and give them different colours. Assign each material to a different sphere.

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\Materials.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\Materials.png" alt="Adding Materials" style="height:200px;"/>
  </a>
</div>
<br><br>

2. Select the parent object. Go to the inspector and add a LOD Group component to it.

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\Add LOD.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\Add LOD.png" alt="Group LOD" style="height:300px;"/>
  </a>
</div>
<br><br>

3. Select LOD 0 (shown in green) and under Renderers add Sphere_LOD0. Add Sphere_LOD1 to LOD 1 and Sphere_LOD2 to LOD 2.

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\Adding Renderers.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\Adding Renderers.png" alt="Adding Renderers" style="height:300px;"/>
  </a>
</div>
<br><br>

You can move the blue camera slider to see how the LOD is applied based on the camera's position. You can also adjust at what percetage the each LOD is applied.

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\LOD Group Camera.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\LOD Group Camera.png" alt="LOD Group Camera" style="height:100px;"/>
  </a>
</div>
<br><br>

Now you know how the LOD Group component works, lets create a more realistic example using a model made in Blender. Don't worry if you don't know Blender, the instructions should guide you through this task. Ask for help if you're not sure.

4. Open Blender. Select New File > General. In the main window, select the camera object. Hold shift and select the cube and the light object. Press the Delete key to delete them. Go to Add > Mesh > Monkey.

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\2 - Add Monkey Mesh.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\2 - Add Monkey Mesh.png" alt="Add Monkey Mesh" style="height:400px;"/>
  </a>
</div>
<br><br>

5. We need to add a Subdivision Component to add detail to this model and make it our LOD 0 model. To do this, select the model, select the blue wrench (shown below).

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\2 - Finding Subdivision Surface.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\2 - Finding Subdivision Surface.png" style="height:700px;"/>
  </a>
</div>
<br><br>

Then select Add Modifier > Subdivision Surface.

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\2 - Add Subdivision Surface.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\2 - Add Subdivision Surface.png" alt="Add Subdivision Surface" style="height:400px;"/>
  </a>
</div>
<br><br>

6. Set the Levels Viewport to the highest it will go (you probably wouldn't do this in reality, but we'll do it for demonstration purposes) to increase the quality. Also add a Decimate modifier. You can leave this modifier for now. We can read our Face Count (the number of flat surfaces on the model) at the bottom of this component.

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\2 - Add Decimate.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\2 - Add Decimate.png" alt="Add Decimate" style="height:500px;"/>
  </a>
</div>
<br><br>

7. Add '_LOD0' to rename Suzanne to ''Suzanne_LOD0. To do this, select the mesh under Scene Collection (the top right window), then press F2 to rename. Make sure you get the spelling correct, Unity will need to use this name later.

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\2 - Monkey Rename.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\2 - Monkey Rename.png" alt="Monkey Rename" style="height:100px;"/>
  </a>
</div>
<br><br>

8. Select Suzanne and duplicate by pressing Shift + D. You'll then be able to move the copied mesh around (like below). Right Click to reset the model to the original position.

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\2 - Dublicate Monkey.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\2 - Dublicate Monkey.png" alt="Duplicate Monkey" style="height:400px;"/>
  </a>
</div>
<br><br>

9. Rename this mesh to 'Suzanne_LOD1'. Select the mesh and then press the M key. Select +New Collection. Accept the default name.

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\2 - New Collection.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\2 - New Collection.png" alt="New Collection" style="height:200px;"/>
  </a>
</div>
<br><br>

10. Make sure you select the eye icon to hide Suzanne_LOD0. Now we can reduce the quality of this mesh. Originally, Face Count was 125,952. Select Suzanne_LOD1 and djust the settings how you wish for LOD1. I used a Levels Viewport of 3 and Decimate Ratio of 0.35 to reduce the Face Count to 15,921.

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\2 - LOD1 Detailing.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\2 - LOD1 Detailing.png" alt="LOD1 Detailing" style="height:600px;"/>
  </a>
</div>
<br><br>

11. Select Collection 2 and Ctrl+C then Ctrl+V it to copy and paste it. Rename the collection to 'Collection 2' and make sure this Suzanne is called 'Suzanne_LOD2'. Disable viewing Suzanne_LOD0 and Suzanne_LOD1 by selecting the eye buttons again (see the image below if you're stuck). Adjust the parameters for this model again. My settings reduced the Face Count to 674.

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\2 - LOD2 Detailing.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\2 - LOD2 Detailing.png" alt="LOD2 Detailing" style="height:400px;"/>
  </a>
</div>
<br><br>

12. Finally, make an LOD3 Suzanne. Maybe it's a bit over the top, but I set my quality really low here for a Face Count of 90.

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\2 - LOD3 Detailing.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\2 - LOD3 Detailing.png" alt="LOD3 Detailing" style="height:400px;"/>
  </a>
</div>
<br><br>

13. Save your model at File > Export > FBX. Save it directly into your Unity Assets Folder.

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\2 - Save.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\2 - Save.png" alt="Saving" style="height:500px;"/>
  </a>
</div>
<br><br>

14. Drag and drop your new 3D model into the Hierarchy. You'll find the LOD Group component already applied! Adjust it how you'd like it. Run some tests to make sure the low-quality model is showing by making LOD3 show early. Notice how you can also see the LODs number of trianges (Face Count) as a percentage of LOD0. 

<div align="center">
  <a href="Images\01 - Discrete LOD Tutorial\2 - LOD in Unity.png" target="_blank">
    <img src="Images\01 - Discrete LOD Tutorial\2 - LOD in Unity.png" alt="LOD in Unity" style="height:400px;"/>
  </a>
</div>
<br><br>

15. Be sure to save this project. You'll need it for the next task.