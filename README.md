# fatiando-notes
Notes on using fatiando family libraries

## Verde
- Useful gridding api
    - Downside, splines etc - so not useable at high resolution

## Harmonica
- Has xarray backed Fast Fourier Transform filter capability
    - This is definitely useable at scale, although of course complex128 datatypes and copies require significant memory    

- Filter gotchas
    - harmonica returns positive y coords, so your maps will be flipped in that sense - np.flipud() type problem
    - or  grid = grid.assign_coords(y = grid.y.data[::-1]) thanks to mg
    - or da = xr.tutorial.open_dataset('air_temperature') https://stackoverflow.com/questions/54677161/xarray-reverse-an-array-along-one-coordinate
        - da.isel(lat=slice(None, None, -1))

- Pseudogravity
    - Notebooks : https://github.com/RichardScottOZ/PFToolbox - thanks to Lu
    - See initial work https://github.com/fatiando/harmonica/pull/299 

- Examples
- https://github.com/fatiando/harmonica/pull/377    



## Old Fatiando package
- Notes on filters
    - https://legacy.fatiando.org/api/gravmag.transform.html#fatiando.gravmag.transform.tilt
