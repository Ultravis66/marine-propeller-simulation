# marine-propeller-simulation
Simulated a marine propeller operating in water using two CFD solvers: OpenFOAM (MRF approach) and STAR-CCM+ (Rigid Body Motion)..

### Velocity Contours and Streamlines
![Rotor Velocity Contours](Rotor_Contour.png)

### Mesh Refinement Overview
![Mesh Refinement Overview](Rotor_mesh1.png)

### Near-Wall Boundary Layer Mesh
![Near Wall Mesh](Rotor_mesh2.png)

### Mesh Setup
- Base mesh generated with **snappyHexMesh**.
- Local refinement around the propeller up to **level 5**.
- **8 prism layers** extruded on the rotor surface with an expansion ratio of **1.2**.
- Estimated first cell height ≈ **4×10⁻⁵ m** (y⁺ ≈ 1–5 in water).
- Refinement region defined by a cylindrical zone (`rotorCyl`) of radius 0.4 m.
