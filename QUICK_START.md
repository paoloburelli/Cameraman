CamOn is a Unity library/plugin that let's the developers and designers control the camera without the hustle of custom scripting or manual placement. It is designed both to simplify the camera placement process in cut-scenes and to allow more cinematographic visualisations during gameplay.
This file contains a few basic steps to start using CamOn and a short description of the components. For the full documentation (including tutorials, videos and demos), please visit the library's GitHub page: ihttps://github.com/paoloburelli/camon.

# UI Quick start
1. Select the objects you want the camera to visualise on the screen and add for each of them an _Actor_ component.
2. Change the _Actor_ component parameters to make the Actor shape match the desired object.
3. Add a _Camera Operator_ component to the main camera, select the desired shot and the actors you want to include in the shot.
4. Press play and check the resul.

# Scripting Quick Start
1. Create an actor: use _Actor.Create ()_ to create an actor and attach it to an object.
2. Select a shot: use _CameraOperator.OnMainCamera.SelectShot()_ to assign a shot to the camera and decide the type of transition.

# Components

## Shot
A shot, in cinematography, describes an uninterrupted series of frames with common composition properties. We employ the shot concept to describe the requirements for the camera behaviour in terms of how the frame generated by the camera should look like. A shot is composed, therefore, by a number of actors – not necessarily humans – and a description of the composition properties of the frames. In the current version, CamOn supports the following five properties that can be used to describe a shot: minimum visible portion of an actor, size of the actor's projected image within the frame, angle at which the actor should be shot, relative position between two actors in the shot, absolute position of an actor in the shot. The library comes with a number of pre defined shots.

## Actor
An actor is a component representing an object in a shot, its purpose is to give a standard representation of different types of objects that can be used throughout the camera control flow to animate the camera. An actor represents the connected object with a proxy geometry that can be adapted to the object’s shape and size.
CamOn comes with 6 shapes that can attached to an object to represent it for the camera: sphere, capsule, cylinder, cube plane and quad. Each shape can be starched and translated to match the desired object's shape and area.

## CameraOperator
The camera operator component is the central component connecting shot, actors and the camera. It instructs the camera with a specific shot and set of actors and, at every frame, it controls the camera animation. 
This component allows control of the camera dynamic behavi_our and it ensures that the camera is animated smoothly guaranteeing frame coherence. The UI includes the possibility to control the reactivity an the speed of the camera, and it gives some feedback about the quality of the current camera position in relation to the currently selected shot.