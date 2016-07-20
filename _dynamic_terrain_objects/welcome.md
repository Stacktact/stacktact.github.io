---
permalink: "/interactive/dynamic_terrain_objects/welcome"
layout: single
author_profile: false
redirect_from:
  - /interactive/dynamic_terrain_objects/

title: "Dynamic Terrain Objects"

sidebar:
  nav: "dynamic_terrain_objects"
---

{% include base_path %}

Runtime modification of Unity Terrain is a tricky problem to solve. Managing the translation of world space into terrain heightmap and alphamap space, modifying those values, and then writing them back to the correct part of the terrain is handled seamlessly by Dynamic Terrain Objects. Here is a quick overview of a few of the features found in the library:

<iframe width="560" height="315" src="https://www.youtube.com/embed/gjUUs_m2u0Q" frameborder="0" allowfullscreen></iframe>
<br />

Check out the [Quick-Start Guide](/interactive/dynamic_terrain_objects/quick_start_guide.html) to get going.

## Library Overview: Deformer class

This is a quick overview of the Deformer class which is the main point of interaction with the library. Drop the Deformer script on
your GameObject and it is now a dynamic terrain object. All "Now" functions are to conveniently set terrain changes and commit them to the 
terrain in one step. For compound deformations (for example: Add and Smooth in one frame) use the non-"Now" versions of each function 
and then call "SetHeights" and/or "SetAlphas" once finished.  Please see the 
[Deformer's detailed class documentation](/interactive/dynamic_terrain_objects/deformer) for more in depth information.

### Attributes 

* terrainAreaPadding
* terrainTextureIndex
* terrainTextureOpacity
* alphaPadding
* AlphaFitType
* HeightFitType
* keepTerrainAreaUpdated

### Public Functions

* AddNow()
* Add()
* SubtractNow()
* Subtract()
* SmoothNow()
* Smooth()
* TextureNow()
* Texture()
* Displace()
* ShowAreaVertices()
* ShowAreaAlphas()
* DestroyDebugObjects()
* UpdateAreaPosition()
* SetHeights()
* SetAlphas()

{% include paginator.html %}
