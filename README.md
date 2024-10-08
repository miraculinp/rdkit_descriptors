# RDKit Molecular Descriptor Calculation - README

## Prerequisites

Ensure you have `rdkit` installed. You can install it using the following command:

```bash
!pip install rdkit
```

## Overview

### 1. **Importing Required Libraries**
   - **pandas**: For data handling.
   - **rdkit**: RDKit modules for handling molecules and calculating descriptors.
   - **warnings**: To suppress unnecessary warnings.

### 2. **Loading the Dataset**
   - The dataset (`PDE4AKI.csv`) is loaded using `pandas`. 

### 3. **Generating Molecular Objects**
   - SMILES strings are converted into RDKit molecular objects using `Chem.MolFromSmiles()`.
   - Hydrogen atoms are added to the molecules using `Chem.AddHs()`.

### 4. **Visualizing Molecules**
   - The first few molecules from the dataset are displayed as images using `Draw.MolsToGridImage()` for visual inspection.

### 5. **Calculating Molecular Descriptors**
   - **Single Molecule Descriptors**: A single molecular descriptor (`RingCount`) is calculated for a specific molecule using `MolecularDescriptorCalculator()`.
   - **Multiple Descriptors for All Molecules**: A full set of molecular descriptors is computed for all molecules in the dataset. The descriptors are listed in `Descriptors._descList`.

### 6. **Generating Descriptor DataFrame**
   - Descriptors for all molecules are calculated and stored in a new DataFrame.
   - The original dataset is updated with the calculated descriptors by concatenating both DataFrames.

### 7. **Exporting the Results**
   - The modified dataset, including all descriptors, is exported to a new CSV file (`PDE4AKI_descriptors.csv`).

## Key Functions and Modules

- **`Chem.MolFromSmiles()`**: Converts a SMILES string to a molecular object.
- **`Chem.AddHs()`**: Adds hydrogen atoms to a molecule.
- **`MoleculeDescriptors.MolecularDescriptorCalculator()`**: Calculates molecular descriptors for a given molecule.
- **`Draw.MolsToGridImage()`**: Generates an image grid of molecules for visualization.
- **`Descriptors._descList`**: List of all available molecular descriptors in RDKit.

## Output

- The script outputs a CSV file (`PDE4AKI_descriptors.csv`) with all the molecular descriptors for the molecules in the dataset, excluding the molecular objects.

## How to Run

1. Install `rdkit` and other necessary libraries.
2. Make sure the `PDE4AKI.csv` file is available in the specified path.
3. Run the script to compute and export molecular descriptors.
