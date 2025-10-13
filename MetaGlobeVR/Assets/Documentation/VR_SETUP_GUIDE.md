# 👓 VR Foundations: Meta XR Setup Guide

This step-by-step guide documents the setup process for VR using the Meta XR All-in-One SDK, ensuring a repeatable process for future students.

## 1. VR Project Configuration
1.  **SDK Import:** Import the **Meta XR All-in-One SDK** from the Asset Store via the Unity Package Manager.
2.  **XR Plug-in Management:** In Project Settings, ensure the **Oculus** provider is checked under the **Android** tab.

## 2. Player and Hand Setup
1.  **Add Rig:** The **OVRCameraRig** is added to the scene to provide the player's head tracking (`CenterEyeAnchor`) and controller/hand tracking (`LeftHandAnchor`, `RightHandAnchor`).
2.  **Remove Default:** The default `Main Camera` must be deleted as the `OVRCameraRig` provides the new head camera.

## 3. Core Interaction Setup (Grab)
The ability to grab the globe relies on two key components:

### A. Making the Object Grabbable
* **Component:** **`OVRGrabbable`**
* **Location:** Attached to the **`Globe`** GameObject.
* **Dependencies:** Requires a **Collider** and **Rigidbody** to function.

### B. Enabling the Grabber
* **Component:** **`OVRGrabber`**
* **Location:** Attached to the **`LeftHandAnchor`** and **`RightHandAnchor`** GameObjects.
* **Function:** This component listens for the controller's grip input and uses raycasting/trigger volumes to search for and interact with nearby objects that have the `OVRGrabbable` component.
