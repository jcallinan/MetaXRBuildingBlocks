# 🌍 MetaGlobe VR: Project Summary

This document serves as the combined report for scene structure, GameObject usage, prefabs, and fundamental C# scripting concepts.

## 1. GameObjects, Components, and Prefabs

The scene uses a clear structure centered on the **`Globe`** object, with reusable **Prefabs** for points of interest (POIs).

### Scene Components Overview
* **`WorldController`:** An empty GameObject acting as the scene's root logic container.
* **`Globe` (3D Sphere):** The main interactive asset. It has a **Sphere Collider** and a **Rigidbody** component (with **Is Kinematic** checked initially).
* **Prefab Usage:** The **`POI_Marker`** prefab is instantiated **five or more times** across the globe, each with a `POI_Interaction.cs` script. This demonstrates effective prefab usage.

[Screenshot of the Unity Hierarchy showing WorldController, Globe, and at least 5 POI_Marker instances]
[Screenshot of the Unity Inspector for the Globe GameObject, showing the Transform, Sphere Collider, Rigidbody, and GlobeRotator script attached]

## 2. C# Basics: Start() and Update()

The core logic is demonstrated in the `GlobeRotator.cs` script.

### Start() Implementation
* **Purpose:** Initialization logic, executed once before the first frame.
* **Code Example:**
    ```csharp
    void Start()
    {
        // Stores the initial rotation of the object as a reference point.
        initialRotation = transform.rotation; 
    }
    ```

### Update() Implementation
* **Purpose:** Continuous game logic, executed once per frame.
* **Code Example:**
    ```csharp
    void Update()
    {
        float horizontalInput = Input.GetAxis("Horizontal");
        // Applies rotation based on input, using Time.deltaTime for frame-rate independence.
        transform.Rotate(Vector3.up, horizontalInput * rotationSpeed * Time.deltaTime, Space.World); 
    }
    ```

## 3. GitHub Submission
All relevant code and documentation files have been pushed to this repository, including the C# scripts (`GlobeRotator.cs`, `POI_Interaction.cs`, `PhysicsGrabber.cs`).
