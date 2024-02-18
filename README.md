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
