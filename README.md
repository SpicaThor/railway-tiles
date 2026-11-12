# Railway tiles

The railway lines and stations of the whole world, cut from OpenStreetMap for
[Axionix](https://spicathor.github.io/)'s train mode: which line a train is on,
its speed limit, tunnels and bridges. Served from here by GitHub Pages:

    https://spicathor.github.io/railway-tiles/v1/root.json

- `v1/root.json`: each layer's regions (z4 tiles) and the hash of their index; the
  OpenStreetMap data's time
- `v1/index/<hash>.json`: a region's tiles
- `v1/tiles/<hash>.bin`: a tile (raw deflate; the format is in `railtiles.py`'s
  docstring in the app's repository)

Every index and tile is named by its contents' hash (SHA-256, first 16 hex), so
they never change and can be cached for good. Only `root.json` changes.

Layers: `passenger` (lines in a passenger route, or high speed, with the
stations) and `other` (every other running line).

## License

The data is © OpenStreetMap contributors and is available under the
[Open Database License](https://opendatacommons.org/licenses/odbl/1-0/) (ODbL).
These tiles are a derived database and are offered under the ODbL as well.
See https://www.openstreetmap.org/copyright.
