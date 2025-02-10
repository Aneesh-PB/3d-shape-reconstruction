# 3D Shape Analysis and Reconstruction

## Overview
This project analyzes a 3D point cloud representing a deformed component, performs Principal Component Analysis (PCA) to determine its principal axes, and reconstructs the shape as a frustum. The analysis includes radius variation along the height and visualization of the original and reconstructed shape using Plotly.

## Dependencies
Ensure you have the following Python libraries installed before running the script:
- `numpy`
- `plotly`
- `scipy`
- `scikit-learn`

You can install missing dependencies using:
```sh
pip install numpy plotly scipy scikit-learn
```

## Files
- **3d_shape_points_data.npz**: Input file containing the 3D point cloud data.
- **script.py**: Python script to analyze and visualize the data.

## Code Workflow
1. **Load the Point Cloud Data**
   - Reads the `.npz` file and extracts the 3D points.

2. **Visualize the Original 3D Point Cloud**
   - Uses Plotly to create a scatter plot of the point cloud.

3. **Perform Principal Component Analysis (PCA)**
   - Determines the principal axes of the 3D shape.

4. **Analyze Radius Variation Along the Height**
   - Computes radius at different height levels.
   - Fits a linear regression model to estimate the frustum shape.

5. **Reconstruct the Frustum Shape**
   - Computes corrected radii based on the fitted model.
   - Converts points to cylindrical coordinates for shape correction.

6. **Visualize the Reconstructed Shape**
   - Displays both the original deformed shape and the reconstructed frustum.

## How to Run
1. Place `3d_shape_points_data.npz` in the same directory as the script.
2. Run the script using:
   ```sh
   python script.py
   ```
3. The output will display interactive 3D visualizations in your browser.

## Expected Output
- A 3D scatter plot of the original point cloud.
- A 3D scatter plot comparing the original deformed shape and the reconstructed frustum.

## Contact
For any questions or issues, feel free to reach out.

