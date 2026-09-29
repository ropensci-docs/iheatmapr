# Convert iheatmapr subcomponents to plotly format

These are generic methods for converting `link{Iheatmap-class}` plot
components to plotly lists. Not intended for end users; exported for
developers seeking to create new Iheatmap subplots. Any new
`link{IheatmapPlot}`, `link{IheatmapShape}`, `link{IheatmapAnnotation}`,
or `link{IheatmapColorbar}` child class should have one of these
methods.

## Usage

``` r
make_trace(x, ...)

make_shapes(x, ...)

make_annotations(x, ...)

make_colorbar(cb, grid)
```

## Arguments

- x:

  [`IheatmapPlot-class`](https://docs.ropensci.org/iheatmapr/reference/IheatmapPlot-class.md),
  [`IheatmapShape-class`](https://docs.ropensci.org/iheatmapr/reference/IheatmapShape-class.md),
  or
  [`IheatmapAnnotation-class`](https://docs.ropensci.org/iheatmapr/reference/IheatmapAnnotation-class.md)
  object

- ...:

  additional arguments specific to component
