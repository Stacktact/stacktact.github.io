---
permalink: "/interactive/dynamic_terrain_objects/quick_start_guide"
layout: single
author_profile: false

title: "Quick-Start Guide"

header:
  overlay_image: "cool_pattern_splash.jpeg"
  caption: ""

sidebar:
  nav: "dynamic_terrain_objects"
---

{% include base_path %}

# Quick-Start Guide

The most general use of a Dynamic Terrain Object is to attach a Deformer script to any game object with a collider, move that object around during runtime using whatever technique you wish, and deform or update textures on the terrain based on the size and shape of the object. Here are the steps to go from a brand new Unity project to a basic implementation. Following this will be a more detailed breakdown of what a Dynamic Terrain Object can do and a then a closer look at the implementation.

1. Import the DynamicTerrainObjects package into Unity via the Asset Store
2. Create a Terrain via the Unity main menu (GameObject -> 3D Objects -> Terrain) or by right clicking in the project Hierarchy (3D Object -> Terrain)
3. Add at least 2 textures to the Terrain
4. Using the built in Terrain editor, set the height of the terrain to something other than zero (ie: 60). This is necessary because Terrain starts out flat and set to its lowest height. If it is already at it's lowest height then operations that would subtract terrain will not make it go any lower.
4. Create a sphere GameObject via the Unity main menu (GameObject -> 3D Objects -> Sphere) or by right clicking in the project Hierarchy (3D Object -> Sphere)
5. Using the Sphere's transform controls, position the object so that it intersects with the terrain.
6. In the Sphere's inspector, click on "Add Component" and search for "Deformer" and add this script to the Sphere object.
7. Click "Add Component" again, but this time select "TestDeformerObject". This is an example of a script you might write that both moves your Deformer around and makes calls that update the terrain. This is a purely demonstrative implementation, but hopefully it will help you understand how to use a Deformer. "TestDeformerObject" is heavily commented; feel free to check out what it is doing!
8. Hit play and watch as the Sphere is moved and the terrain modification functions are called.

{% include paginator.html %}
