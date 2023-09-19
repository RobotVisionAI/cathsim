# CathSim: An Open-source Simulator for Endovascular Intervention
### [[Project Page](https://RobotVisionAI.github.io/cathsim/)] [[Paper](https://arxiv.org/abs/2208.01455)]

## Contents
1. [Requirements](#requirements)
2. [Installation](#installation)
3. [Scripts](#scripts)


## Requirements
1. Unity Hub
2. C# programming language


## Installation

1. Install the Unity Hub
2. Import the project package "haptic-feedback" into Unity, then Run it.

Note: The rope in the scene is representing the guidewire, and the environment is representing the aortic arch.


## Scripts

### 1. CatmullRomSpline.cs
The "CatmullRomSpline" script provides a Catmull-Rom spline interpolation implementation for creating smooth curves between control points

How to Use:

1. Attach the CatmullRomSpline script to an empty GameObject or any GameObject where you need spline interpolation.
2. Create an array of control points (values) that you want to interpolate.
3. Initialize the CatmullRomSpline by calling the constructor with the control points array.
4. Use the GetValue method to interpolate values along the spline at different positions.
5. Use the Test method to do sample interpolation tests
   
   
### 2. MouseDraggable.cs
The MouseDraggable script allows you to click and drag a GameObject with a Rigidbody attached to it, making it follow the mouse cursor's movement, within the Unity game engine. It smoothly moves the object in response to mouse input, temporarily disabling physics simulation for smooth dragging.

How to Use:

1. Attach the MouseDraggable script to the GameObject you want to make draggable. Make sure the GameObject has a Rigidbody component attached.
2. In the Unity Inspector, you will see the MouseDraggable script component. Customize the parameter for Drag Sensitivity. Adjust the drag sensitivity to control how responsive the object is to mouse movement.
3. Play the Unity scene to test the draggable behavior.
4. When you click on the GameObject, it will become draggable by the mouse. You can click and drag it to move it around.
5. Release the mouse button to stop dragging. The GameObject will then resume its normal physics behavior.
   

### 3. RopeController.cs
This script manages a dynamic rope made of interconnected fragments, handles length adjustment, collisions, and provides haptic feedback. 

Features: 
- Dynamic rope with adjustable length
- Collision detection with objects in the environment
- Haptic feedback support for VR and non-VR platforms

How to Use:

1. Requirements:
      - Ensure that you have Unity installed and a compatible version of the Unity XR Plugin if you plan to use VR features.
2. Setup:
      - Attach this script to the GameObject in your scene.
      - Create a prefab for rope fragments and assign it to the fragmentPrefab field.
      - Configure the desired number of fragments, spacing between them, and raycast distance
        for collisions in the inspector.
      - In the Inspector panel, customize the following parameters to suit your project:
         1) Fragment Prefab: Assign a prefab for rope fragments.
         2) Fragment Count: Set the number of rope fragments.
         3) Interval: Specify the spacing between fragments.
         4) Move Speed: Adjust the speed of rope movement.
         5) Rotation Speed: Control the rope's rotation speed.
         6) Raycast Distance: Define the maximum raycasting distance for collisions.
         7) Haptic Manager: Assign the HapticFeedbackManager script if you want to enable haptic feedback.
3. Haptic Feedback:
      - If you're using VR, make sure you have the XR settings configured in your Unity
        project. The script automatically checks for VR support.
4. Layer Configuration:
      - Configure the environment layer in Unity to specify which objects the rope should collide with
      - In Unity, go to Edit -> Project Settings and select Tags and Layers
      - Under Layers, find or create the Environment layer and assign it to objects in your scene that should interact with the rope.
5. Usage:
      - Control Rope Movement:
        During runtime, use the following keyboard input:
         - Up Arrow: Move the rope forward vertically.
         - Down Arrow: Move the rope backward vertically.
         - Left Arrow: Rotate the rope to the left.
         - Right Arrow: Rotate the rope to the right.
      - Adjust Rope Length:
         - Use the Up Arrow to increase the rope's length.
         - Use the Down Arrow to decrease the rope's length. 
6. Collision Handling:
      - The script handles collisions between rope fragments and objects in the environment automatically.
      - When a rope fragment collides with an object tagged as "Environment", collision handling is triggered.
      - If you've configured the HapticFeedbackManager script, it will provide haptic feedback based on the platform (VR or non-VR).


### 4. HapticFeedbackManager.cs
This Unity script provides a simple way to trigger haptic feedback on supported platforms, including mobile devices and VR headsets.

Features:
- Supports haptic feedback on platforms that allow vibration
- Compatible with VR platforms, providing haptic feedback for left and right hand controllers (if supported)
- Easily customizable duration and intensity of the haptic feedback

How to Use:
1. Attach the HapticFeedbackManager script to a GameObject in your Unity scene.
2. Customize the haptic feedback duration and intensity by adjusting the hapticDuration and hapticIntensity variables in the Inspector.
3. Call the TriggerHapticFeedback method from your script or UI button click event to trigger haptic feedback.

   
## Demo
![ai-vr](./ar_vr_unity_cathsim.png)

![ai-vr1](./ar_vr_unity_cathsim_1.png)


## Terms of Use

Please review our [Terms of Use](TERMS.md) before using this project.

## License

Please feel free to copy, distribute, display, perform or remix our work but for non-commercial porposes only.
