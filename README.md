# VRBalls

## Instructions

1. Download the asset package;

2. Make sure XR Interaction Toolkit is installed in the project;

3. Download FMOd project and through FMOD > Edit Settings > Bank Import > Studio Project Path insert path to project's *.exe*;

4. Create an object for scripts AudioManager, FmodEvents and Recorder;

5. Add *Throw Ball* and *Landmark Ball* Prefabs;

6. In the FMODEvents script object, fill events with the FMOD project's correspondent events (english or portuguese for voice cues);

7. Add ObjectInHandSpawner script in the desired controller:
    - Reference - Ball prefab to be created in the controller;
    - Controller - Controller object - **must have an XR Action Based Controller**;
    - Add physical materials with the same name;

8. Instance Tracker must be added to the controller where Landmark VRBalls are being created;

9. Add OnButtonPress script on controller object to add mechanics;
    - Actions to Check > Add Binding > Pick desired controller button depending on what happens on OnPress and OnRelease > Pick controller object (where objectInHandSpawner is) and pick function.

## Object In Hand Spawner

- MakeBall - Creates a copy of the ball in the *Reference* parameter;
- ReleaseBall - Releases a VRBall with a *Throw* tag;
- Landmark Ball - Releases a VRBall with a *Landmark* tag;
- DestroyBall - Deletes the last landmark VRBall created, asking for a confirmation before doing so;
- changeMaterial - Changes a throw ball's material;
- startCount - Starts a 3 second timer that turns on the record sound input feature for the landmark ball;
- resetCount - Resets the timer without starting it;
- updateLandmarkSound - Changes the sound of the landmark that is being created.

## InstanceTracker

- changeLandmarkState - Turns on or off all landmark VRBalls depending on thir current state.

**EffectsControl** may be added to objects or their parents to further define the impact sound of objects and sets of objects.

