# LeanTiler

LeanTiler is a user-story driven approach to providing a set of command line
tools for macOS for building your own MapBox Vector Tile pipeline.

The key learning used by this project comes from [James
Milner's](https://loxodrome.io/) [Tiler](https://github.com/geovation/tiler)
project.

When this `mvp` branch is ready for public use it will be merged here into
`master` and this branch will be removed.

This README will be updated as [user stories tracked in
trello](https://trello.com/b/S3L3a35F/lean-tiler) are implemented.

# README

LeanTyler is a set of simple commands that you can use together extremely easily to
build your own maps for the web or for hybrid mobile applications on iOS and
Android.

In particular, LeanTyler can take shapefile or GeoJSON data and generate a single
layer tileset made up of [MapBox Vector Tiles](mvt.md) from it. It can then
merge tilesets representing different parts of a country, or tilesets
representing different types of feature (layers) of the same part of the
country so that you end up with a final multi-layer tileset represented as
a directory structure of `.mvt` files that you can copy to a server to power a
map.

Finally, LeanTyler has commands for helping you generate a map project that uses
the tiles you have generated.

* TODO: See a demo map covering London using Ordnance Survey Open Local
  data with multiple layers from a single tileset
* [Understand why Vector Tiles and WebGL-based mapping might be benefical to your project](FAB.md)

Note: This initial version of LeanTyler requires that you are running on macOS 10.12 and
have already installed [Homebrew](http://brew.sh).

## Developers

LeanTyler follows [the UNIX
philosophy](https://en.wikipedia.org/wiki/Unix_philosophy) of small programs
that each do one thing well and that can be composed into a flexible pipeline
for producing your vector tiles as well as the maps that use them.

Internally the `tyler` commands use [GDAL](http://www.gdal.org/) and
[tippecanoe](https://github.com/mapbox/tippecanoe) to perform much of the
legwork:

```
brew install gdal tippecanoe
```

To get started, why not download a shapefile for London to experiment with from
the [Ordnance Survey Open Local download
page](https://www.ordnancesurvey.co.uk/opendatadownload/products.html#OPMPLC)?

You'll need to tick the box to the right of the `National Grid Reference
squares` label, in the `Download` column, and then scroll down to select `TQ`
from the list next to the grid squares diagram. Scroll to the very bottom of
the page, click `Continue` and follow the instructions.

Once you've extracted the file you'll have a `data` directory with data in
Shapefile format. Confusingly, a single shapefile is made up of four separate
files, so to work with the `TQ_Roads` data, you'll need `TQ_Roads.shp`,
`TQ_Roads.shp`, `TQ_Roads.shp` and `TQ_Roads.shp`.

TODO: More to follow
