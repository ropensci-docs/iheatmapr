# Iheatmap-class

Class to store complex interactive heatmap objects from iheatmapr
package

## Details

This is a virtual class with two children classes, IheatmapHorizontal
and IheatmapVertical. For IheatmapHorizontal additional main heatmaps
are added horizontally, and for IheatmapVertical additional main
heatmaps are added vertically. For details on accessing certain slots of
this class, see
[`access_component`](https://docs.ropensci.org/iheatmapr/reference/access_component.md)
documentation.

## Slots

- `plots`:

  list of plot element in
  [`IheatmapPlots`](https://docs.ropensci.org/iheatmapr/reference/IheatmapPlots-class.md)
  format

- `shapes`:

  list of shape element in
  [`IheatmapShapes`](https://docs.ropensci.org/iheatmapr/reference/IheatmapShapes-class.md)
  format

- `annotations`:

  list of annotation elements in
  [`IheatmapAnnotations`](https://docs.ropensci.org/iheatmapr/reference/IheatmapAnnotations-class.md)
  format

- `xaxes`:

  list of x axes in
  [`IheatmapAxes`](https://docs.ropensci.org/iheatmapr/reference/IheatmapAxes-class.md)
  format

- `yaxes`:

  list of y axes in
  [`IheatmapAxes`](https://docs.ropensci.org/iheatmapr/reference/IheatmapAxes-class.md)
  format

- `colorbars`:

  list of colorbars in
  [`IheatmapColorbars`](https://docs.ropensci.org/iheatmapr/reference/IheatmapColorbars-class.md)
  format

- `colorbar_grid`:

  colorbar grid parameters in
  [`IheatmapColorbarGrid`](https://docs.ropensci.org/iheatmapr/reference/IheatmapColorbarGrid-class.md)
  format

- `current_xaxis`:

  name of current x axis

- `current_yaxis`:

  name of current y axis

- `layout`:

  list of plotly layout parameters

- `source`:

  source name, for use with shiny

## See also

[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
[`main_heatmap`](https://docs.ropensci.org/iheatmapr/reference/main_heatmap.md),
[`access_component`](https://docs.ropensci.org/iheatmapr/reference/access_component.md)

## Author

Alicia Schep
