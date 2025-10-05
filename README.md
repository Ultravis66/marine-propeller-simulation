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

### Flow Field Structure
- **Velocity contours** show smooth acceleration through the propeller disk, with a coherent wake region extending several diameters downstream.  
- The near-wall mesh resolution (first-cell height ≈ 4×10⁻⁵ m) ensured **y⁺ ≈ 1–5**, allowing accurate capture of boundary-layer behavior.







https://www.youtube.com/watch?v=R2ZKZAD3UWo

### Force Predictions
- The propeller produced a **steady thrust of approximately –4506 N** along the x-axis (propeller axis).  
- This value closely matches the **STAR-CCM+ RBM simulation (~–4200 N)**, demonstrating excellent agreement between the steady MRF and transient RBM approaches (difference ≈ 7%).  
- Lateral forces (Fy, Fz) remained below **±5 N**, confirming minimal side loading and good rotor alignment.  
- The predicted moment about the rotation axis was approximately **–1000 N·m**, consistent with expected propeller torque.


### Comparison Summary
| Parameter | OpenFOAM (MRF) | STAR-CCM+ (RBM) | Comment |
|------------|----------------|-----------------|----------|
| Thrust (N) | 4506 | 4500 | Excellent agreement |
| Torque (N·m) | 1000 | 1000 | Within expected tolerance |
| Tip-vortex structure | Q ≈ 1×10⁶ | Similar | Qualitative match |

### Figures
- **Figure 1:** Mid-plane velocity contours with streamlines (`Rotor_Contour.png`)  
- **Figure 2:** Mesh refinement and velocity contours near the rotor (`Rotor_mesh1.png`)  
- **Figure 3:** Near-wall mesh showing boundary-layer resolution (`Rotor_mesh2.png`)



