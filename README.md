# 3D Shape Reconstruction from Point Cloud

## Overview
This project reconstructs the 3D shape of a deformed component using point cloud data. The reconstruction process involves analyzing the radius variation along the height, fitting a linear model to estimate the frustum shape, and visualizing the original and corrected shapes using Plotly.

## Features
- Loads 3D point cloud data from a `.npz` file.
- Visualizes the original deformed shape in a 3D scatter plot.
- Computes radius variations at different height levels.
- Fits a linear model to approximate the shape as a frustum.
- Reconstructs the shape using cylindrical coordinate transformations.
- Displays both the original and reconstructed shapes using Plotly.

## Dependencies
Ensure you have the following Python libraries installed:

```bash
pip install numpy plotly scipy scikit-learn
```

## File Structure
- `3d_shape_points_data.npz` - The input file containing point cloud data.
- `main.py` - The script for loading, analyzing, and visualizing the point cloud data.
- `README.md` - This documentation file.

## Usage
1. Place the `3d_shape_points_data.npz` file in the working directory.
2. Run the script:

   ```bash
   python main.py
   ```

3. The script will generate two 3D scatter plots:
   - The **original deformed shape** (red points)
   - The **reconstructed frustum shape** (blue points)

## Code Explanation
### 1. Load Point Cloud Data
The script loads a `.npz` file and extracts the 3D point coordinates.

### 2. Visualize Original Point Cloud
A 3D scatter plot is generated to display the original deformed shape.

### 3. Radius Computation and Binning
- The radius of each point is calculated as `sqrt(x^2 + y^2)`.
- The height (`z`) is divided into bins, and the average radius for each bin is computed.

### 4. Frustum Approximation
- A linear regression model fits a line to the **radius vs height** data.
- This estimated frustum equation is used to compute corrected radii.

### 5. Shape Correction
- The corrected radii are converted back to Cartesian coordinates (`x, y`).

### 6. Visualization
- The original and reconstructed shapes are plotted in 3D using Plotly.

## Example Output
Two 3D scatter plots will be displayed:
1. **Original Deformed Shape** (Red)
2. **Reconstructed Frustum Shape** (Blue)

## Notes
- Ensure `3d_shape_points_data.npz` is correctly formatted with a key `"points"` containing a `(N,3)` NumPy array.
- The script assumes the shape resembles a frustum; results may vary for irregular geometries.

## License
This project is open-source and can be freely used and modified.

