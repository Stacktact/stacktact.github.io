---
layout: splash
interactive: "true"
author_profile: false

title: "Mine for gold in the frozen north!"
excerpt: "We specialize in Unity3D and are currently developing a gold mining simulator"

header:
  overlay_image: "mountains_splash.jpeg"
  caption: ""

feature_row:
  - image_path: /interactive/d10_dozer_dirt_push.png
    alt: "D10 Dozer pushing dirt"
    title: "Alter terrain in real time"
    excerpt: "Use heavy machinery with accurately simulated physics to dig and manipulate virtual soil. Prepare your mining area, make sure your logistics chain is efficient, and start processing that paydirt!"
  - image_path: /interactive/frozen_stream.jpg
    alt: "Frozen Stream"
    title: "Manage your resources"
    excerpt: "The gold mining season in the arctic north is only a few months long. Managing your resources efficiently is the key to success during the short summer."
  - image_path: /interactive/gold_bars.png
    title: "Race for the gold!"
    excerpt: 'Will you become a profitable <a href="https://en.wikipedia.org/wiki/Placer_mining">placer miner</a>? Many have tried and failed, but with the right combination of resourcefulness and ingenuity you might strike it rich!'

dynamic_terrain_objects:
  background_image: /images/interactive/dynamic_terrain_objects.png
  caption: Run time deformation of Unity terrain using any GameObject 
  asset_url: /interactive/dynamic_terrain_objects/welcome

---

{% include base_path %}

# Untitled Gold Mine Management Simulator

{% include feature_row %}

# Unity Assets

<div class="page__hero--overlay" style="background-image: url('{{ page.dynamic_terrain_objects.background_image }}');">
  <div class="wrapper"> 
    <h1 class="page__title">Dynamic Terrain Objects</h1>
    <p class="page__lead">{{ page.dynamic_terrain_objects.caption | markdownify | remove: "<p>" | remove: "</p>" }}</p>
    <p><a href="{{page.dynamic_terrain_objects.asset_url}}" class="btn btn--info btn--large"><i class="fa fa-share"></i> Find Out More</a></p>
  </div>
</div>

{% include paginator.html %}
