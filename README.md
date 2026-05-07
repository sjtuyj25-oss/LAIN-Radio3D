# LAIN-Radio3D
Low-altitude intelligent network Radio3D dataset

## Description

* **antennas / antennas_test**:
  Antenna configuration maps for training and test sets.

* **gain / gain_test**:
  Ground-truth radio maps corresponding to each antenna configuration.

* **buildings**:
  3D mesh representations of the environment (OBJ).

* **buildings_map**:
  Binary occupancy maps indicating building presence.

* **buildings_heightmap**:
  Height maps describing vertical structure of buildings.

## Data Alignment

All data modalities are strictly aligned through a unified naming convention.

### File Naming Rule

Each sample follows the format:

```
<sceneID>_000_pos_<x>_<y>_<z>.png
```

For example:

```
601_000_pos_209_216_7.png
```

* **sceneID (e.g., 601)**:
  Identifies the environment scene, corresponding to the building information.

* **(x, y, z) = (209, 216, 7)**:
  3D coordinates of the transmitter.

---

### Data Correspondence

For a given filename:

```
601_000_pos_209_216_7.png
```

the following data are aligned:

* `antennas/601_000_pos_209_216_7.png`
* `gain/h*/601_000_pos_209_216_7.png`
* `buildings (scene 601)`

---

### Height-Dependent Radio Maps

Radio maps are further organized by receiver height:

```
gain/
├── h1/
├── h2/
├── h3/
...
```

* Each subfolder `h*` corresponds to a specific receiver height.
* For a fixed scene and transmitter location, radio maps across different heights share the same filename.

Example:

```
gain/h1/601_000_pos_209_216_7.png
gain/h20/601_000_pos_209_216_7.png
gain/h120/601_000_pos_209_216_7.png
```

These represent radio maps under identical conditions but at different receiver heights.

---

### Summary

* Filename → determines **scene + transmitter position**
* Folder (`h*`) → determines **receiver height**
* Same filename across folders → **same spatial configuration**



