---
permalink: "/interactive/dynamic_terrain_objects/quick_start_guide"
layout: single
author_profile: false

title: "Quick-Start Guide"

sidebar:
  nav: "dynamic_terrain_objects"
---

{% include base_path %}

# Quick-Start Guide

The most general use of a Dynamic Terrain Object is to attach the Deformer script (found at the root of the package) to any game object with a collider, move that object around during runtime using whatever technique you wish, and then deform or update textures on the terrain based on the size and shape of the object. 

Here are the steps to go from a brand new Unity project to a basic implementation. If you like, you can also just [check out a detailed documentation of the primary API](/interactive/dynamic_terrain_objects/deformer)

1.  Import the DynamicTerrainObjects package into Unity via the Asset Store
    
    ![Import Package](/images/dynamic_terrain_objects/quick_start/01_import_package.png)

2.  Create a Terrain via the Unity main menu (GameObject -> 3D Objects -> Terrain) or by right clicking in the project Hierarchy (3D Object -> Terrain)

    ![Create Terrain](/images/dynamic_terrain_objects/quick_start/02_create_terrain.png)

3.  Add at least 2 textures to the Terrain.

    ![Add Textures to Terrain](/images/dynamic_terrain_objects/quick_start/03_terrain_texture.png)

4.  Using the built in Terrain editor, set the height of the terrain to something other than zero (ie: 300) using the flatten tool. This will raise the entire terrain up to half of its default max height. This is necessary because Terrain starts out set to its lowest height by default. When terrain is at its lowest height it cannot be lowered any further making subtract operations impossible.

    ![Flatten Terrain](/images/dynamic_terrain_objects/quick_start/04_flatten_terrain.png)

5.  Create a sphere GameObject via the Unity main menu (GameObject -> 3D Objects -> Sphere) or by right clicking in the project Hierarchy (3D Object -> Sphere)

    ![Create Sphere](/images/dynamic_terrain_objects/quick_start/05_create_sphere.png)

6.  Using the Sphere's transform controls, position the object so that it intersects with the terrain.

    ![Position Sphere](/images/dynamic_terrain_objects/quick_start/06_position_sphere.png)

7.  In the Sphere's inspector, click on "Add Component" and search for "Deformer" and add this script to the Sphere object.

    ![Add Deformer Script](/images/dynamic_terrain_objects/quick_start/07_add_deformer.png)

8.  Click "Add Component" again, but this time select "TestDeformerObject". This is an example of a script you might write that both moves your Deformer around and makes calls that update the terrain. This is a purely demonstrative implementation, but hopefully it will help you understand how to use a Deformer. "TestDeformerObject" is heavily commented; feel free to check out what it is doing!

    ![Add Test Deformer Script](/images/dynamic_terrain_objects/quick_start/08_add_test_deformer.png)

9.  Hit play and watch as the Sphere is moved and the terrain modification functions are called.

{% include paginator.html %}
