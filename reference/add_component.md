# Adding plot components to iheatmapr

These are generic methods for adding new plot components to an
`link{Iheatmap-class}` object. Not intended for end users; exported for
developers seeking to create new Iheatmap subplots.

## Usage

``` r
add_axis(p, new_axis, ...)

add_colorbar(p, new_colorbar, ...)

add_plot(p, new_plot, ...)

add_shape(p, new_shape, ...)

add_annotation(p, new_anno, ...)
```

## Arguments

- p:

  [`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
  object

- new_axis:

  new
  [`IheatmapAxis-class`](https://docs.ropensci.org/iheatmapr/reference/IheatmapAxis-class.md)
  object

- new_colorbar:

  new
  [`IheatmapColorbar-class`](https://docs.ropensci.org/iheatmapr/reference/IheatmapColorbar-class.md)
  object

- new_plot:

  new
  [`IheatmapPlot-class`](https://docs.ropensci.org/iheatmapr/reference/IheatmapPlot-class.md)
  object

- new_shape:

  new
  [`IheatmapShape-class`](https://docs.ropensci.org/iheatmapr/reference/IheatmapShape-class.md)
  object

- new_anno:

  new
  [`IheatmapAnnotation-class`](https://docs.ropensci.org/iheatmapr/reference/IheatmapAnnotation-class.md)
  object
