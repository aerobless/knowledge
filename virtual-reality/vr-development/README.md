---
description: >-
  This probably could also be a page on game development, but since I'm mainly
  interested in game development for VR it's named as such.
---

# VR Development

## Unity Notes

* **Audio**
  * [Spatial audio source settings](https://subscription.packtpub.com/book/game_development/9781787286450/1/01lvl1sec12/3d-sound-and-spatial-blending)
* **Realtime Rendering**
  * [Unity HDRP vs URP](https://www.youtube.com/watch?v=5MuA92xUJCA)
* **Programming/IDE**
  * [Rider doesn't autocomplete Unity classes:](https://rider-support.jetbrains.com/hc/en-us/community/posts/360010059320--Resolved-RIDER-2020-02-04-Rider-doesn-t-autocomplete-anything-from-Unity) Editor is probably not set correctly
  * [Rotate gizmo correctly with player](https://stackoverflow.com/questions/57982000/how-to-change-the-orientation-for-an-overlapbox-and-a-gizmo) 
* **Characters**
  * [Have NPC sit in a a chair](https://www.youtube.com/watch?v=bRIpwQUUN24)
  * [Setting up ragdoll physics in Unity](https://www.youtube.com/watch?v=DInV-jHm9rk)
  * [Active idle: have NPC move head with dynamic animations](https://www.youtube.com/watch?v=T7AdzwW7n2I)
    * [Procedural animations \(Animation Rigging\)](https://www.youtube.com/watch?v=saOHaHKSOi0&t=1s)
  * [Inverse kinematics for grabbing things](https://docs.unity3d.com/Manual/InverseKinematics.html)
    * [Smooth grab speed](https://forum.unity.com/threads/how-to-smooth-ik-setikpositionweight.324836/)
* Physics
  * [Performance Optimizations](https://www.youtube.com/watch?v=pTz3LMQpvfA)
    * [NonAlloc Collider Collection](https://youtu.be/pTz3LMQpvfA?t=617)

## Problems & Solutions

* Particles are only visible on one eye & looking weird/disappearing on the other This may be due to [single-pass rendering \(default\) vs multi-pass rendering.](https://docs.unity3d.com/2020.1/Documentation/Manual/SinglePassStereoRendering.html) Changing this to multi-pass rendering may fix the problem but require more resources. 

## Resources

In the context of this section free means that the resources can be used both commercial and non-commercial without paying a fee. Depending on the license attribution may be required however.

### Textures

* [Textures.com:](https://www.textures.com/library) Get 15 free textures per day
* [Unsplash:](https://unsplash.com/) Lots of free images, typically not texturized yet but high quality none the less

### Sounds

* [Freesound.org: ](https://freesound.org/)A ton of free sound effects and even some music. Generally free, but most assets require attribution under CC3.0 and some assets may not allow commercial use \(cc-nc3.0\). Be sure to check the license for each asset.

### Animations

* [Mixamo](https://www.mixamo.com/#/): Auto-rigging and free animations. 
* [Carngie Mocap Lib \(Unity Store\)](https://assetstore.unity.com/packages/3d/animations/huge-fbx-mocap-library-part-1-19991)

### Various \(game objects, models, textures, sounds, scripts\)

* [Unity Asset Store:](https://assetstore.unity.com/) Another good place to get free or cheap resources is the unity asset store. Generally it is also possible to only use parts of an asset. E.g. if you need medieval textures for your own model you could still get a medieval town asset and just use the textures on your own models. Beware though that copyright applies and you should probably not upload any third party resources to a public VCS. Distributing those assets as part of a game though is fine. 



