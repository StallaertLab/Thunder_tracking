# Thunder_tracking
Pipeline to track movies from Thunder with Ultrack. Prepares for using Track Gardener.

**00_lif_to_zarr.ipynb**

input:

- lif file containing a movie to be tracked

output:

- channels of the movie saved as separate zarr files

**01_segment_test_and_view.ipynb**

- this is an optional step to easily check different segmentation approaches
- by choosing start and stop accross dimensions select a small subset for tests

input:

- channel to be tracked (zarr)

output:

- None

**02_segment.ipynb**

input:

- channel to be tracked (zarr)

output:

- segmented masks (zarr)
- dir with png masks (can be deleted)

**03_run_ultrack.ipynb**

- run in the environment dedicated to ultrack
- use gurobi optimizer if possible

input:

- masks (zarr)

ouput:

- database with the tracking solution (Ultrack format)
- optional: masks labeled by tracks (zarr)

**04_view_tracking.ipnb**

- a short script to visualize tracked labels in napari
