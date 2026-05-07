# LAIN-Radio3D
low-altitude intelligent network Radio3D dataset

## Description

* **antennas / antennas_test**:
  Antenna configuration maps for training and test sets.

* **gain / gain_test**:
  Ground-truth radio maps corresponding to each antenna configuration.

* **buildings**:
  3D mesh representations of the environment.

* **buildings_complete**:
  Binary occupancy maps indicating building presence.

* **buildings_heightmap**:
  Height maps describing vertical structure of buildings.

## Data Alignment

Each sample is spatially aligned across all modalities:

* antennas[i] ↔ gain[i] ↔ building information
* antennas_test[i] ↔ gain_test[i] ↔ building information

