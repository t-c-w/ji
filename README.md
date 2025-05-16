# ji
An illustration of various embeddings

To install:	```pip install ji```

## Overview
The `ji` package provides a comprehensive suite of tools for embedding high-dimensional data into two dimensions using various techniques from the scikit-learn library. This is particularly useful for visualization, data compression, and improving the performance of machine learning algorithms on high-dimensional datasets. The package includes methods such as PCA, LDA, Isomap, Locally Linear Embedding (LLE), and t-SNE among others.

## Main Features
- **Dimensionality Reduction**: Simplify high-dimensional data to two dimensions using various statistical and machine learning methods.
- **Visualization**: Includes a function to create scatter plots of the embedded data, aiding in visual analysis.
- **Extensible**: Easily extendible to include more embedding methods or custom plotting functions.

## Usage Examples

### Basic Usage
To use the `ji` package to analyze and visualize embeddings, you can follow these steps. This example assumes you have a dataset `X` with corresponding labels `y`.

```python
from ji import analyze

# Assuming X and y are already defined
analyze(X, y)
```

### Using with Default Digits Dataset
If you do not specify `X` and `y`, `analyze` will load a pre-defined dataset of handwritten digits (6 classes) and perform the analysis on it.

```python
from ji import analyze

analyze()
```

### Custom Plot Function
You can also pass a custom plotting function to `analyze` to change how the embeddings are visualized.

```python
from ji import analyze
import matplotlib.pyplot as plt

def custom_plot(X, y):
    plt.scatter(X[:, 0], X[:, 1], c=y, cmap='viridis', edgecolor='k')

analyze(plot_fun=custom_plot)
```

## Documentation

### `scatter_plot(X, y)`
Plots a simple scatter plot of the data.
- **Parameters**:
  - `X`: 2D numpy array, the data points to plot.
  - `y`: 1D numpy array, the target labels for coloring the points.

### `analyze(X=None, y=None, plot_fun=scatter_plot, data_name='data')`
Main function to perform and visualize various embeddings.
- **Parameters**:
  - `X`: 2D numpy array, the input data. If `None`, a default dataset (digits) is loaded.
  - `y`: 1D numpy array, the target labels corresponding to `X`. Required if `X` is not `None`.
  - `plot_fun`: Function used to plot the embedding. Defaults to `scatter_plot`.
  - `data_name`: String, a name for the dataset to be displayed in plot titles.
- **Embedding Techniques**:
  - Random Projection
  - PCA (Principal Component Analysis)
  - LDA (Linear Discriminant Analysis)
  - Isomap
  - Standard LLE (Locally Linear Embedding)
  - Modified LLE
  - Hessian LLE
  - LTSA (Local Tangent Space Alignment)
  - MDS (Multidimensional Scaling)
  - Random Trees Embedding
  - Spectral Embedding
  - t-SNE (t-Distributed Stochastic Neighbor Embedding)

This package is designed to be a practical tool in both educational and research settings for those interested in the field of machine learning, data science, and pattern recognition.