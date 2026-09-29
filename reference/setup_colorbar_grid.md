# setup_colorbar_grid

function to set parameters controlling colorbar placement in Iheatmap
object

## Usage

``` r
setup_colorbar_grid(
  nrows = 3,
  y_length = y_spacing * 0.9,
  x_spacing = 0.16,
  y_spacing = y_start/nrows,
  x_start = 1.05,
  y_start = 0.9
)
```

## Arguments

- nrows:

  number of rows in colorbar grid

- y_length:

  length of colorbar

- x_spacing:

  spacing along horizontal axis between colorbars

- y_spacing:

  spacing along vertical axis between colorbars

- x_start:

  left most position of colorbar grid

- y_start:

  top most position of colorbar grid

## Value

[`IheatmapColorbarGrid-class`](https://docs.ropensci.org/iheatmapr/reference/IheatmapColorbarGrid-class.md)
object

## Examples

``` r

cb_grid <- setup_colorbar_grid(nrows = 2, x_spacing = 0.2)
mat <- matrix(rnorm(24), nrow = 6)
hm <- iheatmap(mat, colorbar_grid = cb_grid, cluster_rows = "kmeans",
         cluster_cols = "kmeans", row_k = 3, col_k = 2)

# Print heatmap if interactive session 
if (interactive()) hm 
```
