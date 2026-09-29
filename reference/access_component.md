# Access subcomponents of Iheatmap object

These are methods for accessing subcomponents of the Iheatmap object

## Usage

``` r
# S4 method for class 'Iheatmap'
colorbars(x, what = c("all", "continuous", "discrete"))

# S4 method for class 'Iheatmap'
yaxes(p, xaxis = NULL)

# S4 method for class 'Iheatmap'
xaxes(p, yaxis = NULL)

# S4 method for class 'Iheatmap'
plots(x)

# S4 method for class 'Iheatmap'
shapes(x)

# S4 method for class 'Iheatmap'
annotations(x)
```

## Arguments

- x:

  [`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
  object

- xaxis:

  name of xaxis

- yaxis:

  name of yaxis
