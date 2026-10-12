# KML Zone Numberer

Renumber the zones (polygons) in a KML or KMZ file in a sensible order, check it on a map, then download the renamed KML and an Excel list of old vs new names.

**Use it here:** https://tymondomanko.github.io/KML-Zone-Numberer/

Everything runs in your browser. Your files are never uploaded anywhere.

## How to use

1. Drop a `.kml` or `.kmz` file onto the page (or click to choose one). Files exported from Google My Maps or Google Earth work.
2. Pick an ordering method and check the numbers on the map.
3. Fix any zones by hand by dragging numbers on the map or rows in the list.
4. Download the renamed KML and, if you want it, the Excel name list.

## Ordering methods

| Method | What it does |
| --- | --- |
| Rows | Top row first, reading west to east, then the next row down |
| Columns | Left column first, reading north to south |
| Snake rows | Like rows, but every second row runs east to west, so the walk never doubles back |
| Smart path | Shortest walking route through every zone. Click a zone to start from it |
| Spiral | Winds outward from the middle of the site. Click a zone to make it the centre |
| Clustered | Follows a space-filling curve so nearby zones get nearby numbers |
| Clock sweep | Sweeps around the centre like a clock hand, starting at 12 o'clock |
| Size | Largest zone gets number 1 |

The **row grouping** slider controls how far apart two zones can be and still count as the same row. Raise it if a slightly offset zone jumps into the wrong row. **Reverse** flips any method.

## Fixing the order by hand

- **On the map:** drag a number tag onto another zone. With the default *Swap, then recalculate the rest*, the two zones trade numbers, everything before the lower number stays locked, and the method re-runs for everything after it. Smart path continues the route from the zone you moved. *Swap only* and *Insert and shift the rest* are in the **Map drag** menu.
- **In the list:** drag the ⠿ handle, or focus it and use the arrow keys.
- **Reset to method** undoes all hand edits.

## Naming

- Prefix and suffix, e.g. `Zone ` + number.
- Start number and zero padding (`Zone 01`).
- Row letters for the grid methods (`A1, A2, B1…`).
- Optionally keep the old name after the new number.
- By default only polygons are numbered. Pins and lines keep their names unless you untick the option.

## Outputs

- **Renamed KML**: the original file with only the `<name>` of each numbered placemark changed. Styles, folders, descriptions and other data are kept.
- **Excel name list (.xlsx)**: order, new name, old name, and the latitude/longitude of each zone's label point.

## Base maps

Streets (© OpenStreetMap contributors © CARTO) or satellite (Esri World Imagery), or none. Number tags sit at the point deepest inside each zone, so they stay inside C, L and U shaped zones.

## Running offline

`index.html` is a single self-contained page. Download it and open it in a browser. It needs an internet connection only for the fonts, base map tiles and the KMZ/Excel libraries (loaded from cdnjs).
