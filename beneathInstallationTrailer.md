# BENEATH Installation Trailer

![Title img](img/Beneath.PNG)

## Goal

For this project I wanted to create a trailer for my orientation project BENEATH, so that I can submit the installation to different festivals and people can get a better impression of it. I started this project because I became aware of the company Rokoko. On their website, they presented a method for doing motion capture with [just a webcam](https://vision.rokoko.com/). I wanted to try it out and use it directly to create added value. A video of the trailer on YouTube can be found [here](https://www.youtube.com/watch?v=l0b5yEUcHmM)

### Implementation

To get whats happening in the interactive installation in sync with a motion capture of a person interacting with the installation and then merging this together in Blender would require these steps:

- Setting up my installation *BENEATH* on my PC so I can screen recording
  - Kinect in front of my screen to interact with
- Set up webcam at the same position for motion capture
- Record both whats happening in the installation while also recording via the webcam
- Uploading to *Rokoko* for generating motion capture data
- Rigging the data onto a 3d model within *Rokoko*
- Bringing the rigged model into blender
- Bringing the screen recorded installation video file into blender
  - Video file must be two separate files (not in the end)
    - On is the left side of the projection and the other one the right to make it possible for projecting textures onto the wall in blender
    - In the ende that didn't work because the rendering in cycles would have taken too long so I switched to the *Evee* renderer and faked the light strokes from the projectors 
      - This I did by keyframing color changes in the light shafts in relation to the average color of the emitting texture of the faked projection surface 
- Build a 3d space where the rigged character can perform its movements in a space that kind of looks like an exhibition
  - Projection wall that emits the installation video file
  - Ceiling
  - Kinect inside of a box
  - 2 projectors that have two spotlights in front of them
    - Some truss elements where the projectors hang from
- Place motion capture and video file onto the same first keyframe
- Setup different Camera angles with movement
- Render single PNG's
- Render PNG-sequence together with sound from the screen recording from Adobe Premiere

### Learnings

- Simple Motion Capture
- Animation in Blender
- Performance advantages Evee over Cycles
- organizing screen capture with motion capture
- Rigging character
- Texturing a Character