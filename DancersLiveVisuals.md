# Dancers Live Visuals

![Title img](img/DancersPreviewPic.PNG)

## Goal

I wanted to extend my visual-setup in vvvv-beta, which I use when supporting various bands in a live context. Therefore I had the Idea of oversized dancers, that would be able to adjust their dance moves to the actual mood of the music. In my mind they should have been able to switch between different poses or dance moves and also should be able adjust their speed of the dance. My icing on the cake would be to deform the dancers into obscure creatures to have the opportunity to go into more abstract visual areas when the music does so too.
A demonstration video can be found [here](https://www.youtube.com/watch?v=Pj4o0gpywW8)

## Implementation

- I found a free 3d character on [turbosquid.com](https://www.turbosquid.com/3d-models/basemesh-1741353)
- [Mixamo](https://www.mixamo.com/#/) gives away a huge collection of standard poses and dance moves
  - To have more visual variety I downloaded each 22 different poses and 22 dance-moves
  - rigging was done with the help of the Mixamos     rigging system in the browser
- To be able to blend between different poses and dance moves I needed to put them all into the model. This is done the following way:
  - download all poses and moves without the character
  - import character with rigged t-pose into blender
  - copy all .fbx poses and moves into the rigged character
  - exporting the character as .fbx model with all the animations
- in vvvv-beta I found a useful plugin to make working with skeletons and their animations a lot easier: [mp.dx](https://beta.vvvv.org/contributions/packs/mp-dx/index.html)
  - With this plugin I can import the .fbx character-model that I exported  from Blender and read back every animation and pose
- To make the models dance and actually usable for live-performances I wrote a control program that is making use of several midi controllers and is basically structured as follows:
  - midi controller Note-presses are read Back
  - every note-press is used for filtering out one random dance moves or pose from the predefined array
  - Midi CC-values are being used for:
    - fading from pose to dance
    - adjustment of filtertime between change of pose or dance
    - start and pause / speed adjustment of dance
    - adjustment of obscure transformation offset
- Most of the time I make use of a wider projection format on stage, so I wanted to have three dancers because one would leave a lot of empty space. And dancing alone is no fun anyway.
  - That's why I placed two more dancers in the scene and had similar midi-mappings on them
  - To make it visually more appealing every dancer got it's own texturing to distinguish them from each other

## Learnings

With this project to have another visual setup for live-performances in my pocket I learned the following:

- basics of rigging skeletons
- animations in blender
- using the plugin mp.dx
- how to have multiple poses and animations baked into a character like in a normal game
  - stacking them in a .fbx file
  - filter out single animations and poses for real-time purposes
  - mixing of animation and poses
  - transforming animations
- how to adapt normal game "mechanics" for live-performances with a musical background by using suitable parameters in combination with midi mappings
- real time texturing of a character
