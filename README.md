# sink_simulation_vof
A simple starter template for VOF simulations in OpenFOAM.
Created as a hobby project for learning and sharing.

![sink_simulation_overview](https://github.com/user-attachments/assets/1ab74e78-7e75-4c38-8342-b6c9f337c4a3)

# Requirements
* OpenFOAM v12 (or compatible version)
* ParaView (for visualization)

# How to Run
1. Create the geometry and export the surfaces as STL files: `"walls.stl"`, `"slde.stl"`, `"atmosphere.stl"`, `"atmosphere2.stl"`. *Note: make sure the files are exported in [m] (meters), not [mm].*

2. Copy the STL files into the `constant/triSurface/` directory.

3. Generate the mesh by running:

```bash
blockMesh                    # create base mesh
surfaceFeatures              # extract surface features
snappyHexMesh -overwrite     # snap an refine mesh
```

4. Run the simulation with the solver:
```
incompressibleVoF
```

# Example Results
After running the case, you can open the results in ParaView:

```
paraFoam
```
Example visualization of the fulid interface:

https://github.com/user-attachments/assets/17288ce4-c4b4-43d8-bbf5-77aca4e7f71c

# Note
* This is an unofficial starter case for educational and experimental purposes.
* For research or production use, please adapt and validate the setuo accordingly.
