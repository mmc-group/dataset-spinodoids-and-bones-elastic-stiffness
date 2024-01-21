# dataset-spinodoids-and-bones-elastic-stiffness
Dataset for the publication: 

W. Deng, S. Kumar, A. Vallone, D.M. Kochmann, and J.R. Greer,  "**AI-Enabled Materials Design of Non-periodic 3D Architectures with Predictable Direction-dependent Elastic Properties**", Advanced Materials, TBD, DOI: TBD.

## File and data column descriptions

- **`Deng_et_al_spinodoid_dataset.csv`**: This file contains the homogenized anisotropic elastic stiffness of spinodoids; used for training and testing the machine learning models (ML). The ML code from Kumar et al., Npj Comput. Mater. 2020, 6 (DOI: 10.1038/s41524-020-0341-6) is used and which is available here: https://github.com/mmc-group/inverse-designed-spinodoids.

| Columns  | Description |
| :-------------: |:-------------|
| `volFrac` | Spinodoid relative density or volume fraction $\rho$ |
| `thetaX` | Spinodoid design parameter $\theta_1$ |
| `thetaY` | Spinodoid design parameter $\theta_2$  |
| `thetaZ` | Spinodoid design parameter $\theta_3$ |
| `stiffness`$k$ | Homogenized anisotropic stiffness component of the spinodoid corresponding to the design parameters $(\rho,\theta_1,\theta_2,\theta_3)$. Here, $k$ denotes zero-indexed serialized index of the 6x6 stiffness matrix ($C$) in Voigt notation. E.g., `stiffness8` denotes $C_{23}$. Due to orthotropic symmetry and alignment of principal axes with coordinate system, only the 9 non-zero stiffness components are listed.|

</br>

---

</br>

- **`Deng_et_al_bones_dataset.csv`**: This file contains the homogenized anisotropic elastic stiffness of bone samples used for inverse design benchmark of the ML models. It also contains the spinodoid design parameters obtained from inverse design to match the bone samples and the corresponding homogenized anisotropic elastic stiffness of the spinodoids.

| Columns  | Description |
| :-------------: |:-------------|
| `name` | Bone sample (see `Deng_et_al_bone_image_data` description for reference)  |
| `volFrac`  | Bone relative density or volume fraction |
| `alpha_radians`  | Angle (in radians) of rotation about $x_3$ axis involved in obtaining orthotropic approximation of the bone sample  |
| `beta_radians`  | Angle (in radians) of rotation about $x_1$ axis involved in obtaining orthotropic approximation of the bone sample  |
| `gamma_radians`  |  Angle (in radians) of rotation about $x_2$ axis involved in obtaining orthotropic approximation of the bone sample  |
| `C`$k$  | Homogenized anisotropic stiffness component of the bone sample. Here, $k$ denotes zero-indexed serialized index of the 6x6 stiffness matrix ($C$) in Voigt notation. |
| `Corth`$k$  | Orthotropic approximation of the homogenized anisotropic stiffness component of the bone sample. Here, $k$ denotes zero-indexed serialized index of the 6x6 stiffness matrix ($C$) in Voigt notation. |
| `contrast`  | Young's modulus of the base material: $E_s$ (arbitrary choice)  |
| `spin_volFrac`  | Spinodoid relative density or volume fraction  $\rho$ (obtained from inverse design to match the bone stiffness)  |
| `spin_thetaX`  | Spinodoid design parameter $\theta_1$ (obtained from inverse design to match the bone stiffness)  |
| `spin_thetaY`  | Spinodoid design parameter $\theta_2$ (obtained from inverse design to match the bone stiffness)  |
| `spin_thetaZ`  | Spinodoid design parameter $\theta_3$ (obtained from inverse design to match the bone stiffness)  |
| `spin_Corth`$k$  | Homogenized anisotropic stiffness component of the inverse-designed spinodoid sample, in the same coordinate frame as the orthotropic approximation of bone stiffness.  |
| `spin_C`$k$  | Homogenized anisotropic stiffness component of the inverse-designed spinodoid sample, in the same coordinate frame as the original bone stiffness.  |
| `spin_Rinv`$ij$  | 3D Rotation matrix to go from the coordinate frame of `spin_Corth` to that of `spin_C`. Here, $ij$ denotes the component $i^\text{th}$ row and $j^\text{th}$ column component of the 3x3 matrix. |

</br>

---

</br>

- **`Deng_et_al_bone_image_data`**: This folder contains the 3D image data of the bone samples. 
    - Each bone sample is represented by a 100x100x100 grayscale matrix.
    - Each data is stored in `.mat` which can be parsed directly into the matrix form in MATLAB.
    - The samples were extracted from much larger micro-CT images of the database:
    **Javad Hazrati-Marangalou (2013): Database of femur samples. Version 1. 4TU.ResearchData. Dataset. https://doi.org/10.4121/uuid:4ae59365-92f0-480b-a899-ade34bc84a00**. Please also cite this reference as original source if you use the extracted image data from our dataset.
    - File nomenclature convention: `XXXX_bY.mat` denotes the `Y`-th small sample extracted from the original 3D image/FEM file `FEM0XXXX` by Javad Hazrati-Marangalou (2013). The numbering choice of `Y` is arbitrary.


</br>

---

</br>

## Citation
If you use this data, please cite the publication: W. Deng, S. Kumar, A. Vallone, D.M. Kochmann, and J.R. Greer,  "**AI-Enabled Materials Design of Non-periodic 3D Architectures with Predictable Direction-dependent Elastic Properties**", Advanced Materials, TBD, DOI: TBD.


Shield: [![CC BY-NC 4.0][cc-by-nc-shield]][cc-by-nc]

This work is licensed under a
[Creative Commons Attribution-NonCommercial 4.0 International License][cc-by-nc].

[![CC BY-NC 4.0][cc-by-nc-image]][cc-by-nc]

[cc-by-nc]: http://creativecommons.org/licenses/by-nc/4.0/
[cc-by-nc-image]: https://licensebuttons.net/l/by-nc/4.0/88x31.png
[cc-by-nc-shield]: https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg




