# Thunder_tracking
Pipeline to track movies from Thunder with Ultrack. Prepares for using Track Gardener.

**00_lif_to_zarr.ipynb**

input:

- lif file containing a movie to be tracked

output:

- channels of the movie saved as separate zarr files

**01_segment.ipynb**

input:

- channel to be tracked (zarr)

output:

- masks (zarr)

**02_run_ultrack.ipynb**

- run in the environment dedicated to ultrack
- use gurobi optimizer if possible

input:

- masks (zarr)

ouput:

- database with the tracking solution (Ultrack format)
- optional: masks labeled by tracks (zarr)

**03_translate_db.ipynb**

input:

- database with the tracking solution (Ultrack format)

output:

- database with the tracking solution (Track Gardener format)
