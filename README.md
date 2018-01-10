Kilonova model survey 2017
---------------------------
Feel free to make use of these models, referencing Kasen et al. 2017

These models provide synthetic spectral times - the UV to IR spectrum at every 0.1 days after merger.
From the spectral time series, light curves can be constructed in any filter of interest.

The models are derived from a full solution of the time-dependent radiative
transfer equation, which self-consistently solves for the thermal and ionization/excitation
state of the ejecta under local thermodynamic equilibrium. The multi-wavlength opacities
are calculated using atomic data for millions of bound-bound line transitions, including
all lanthanides. Noise in the models is due to Monte Carlo sampling, and can be reduced by averaging
over a longer time frame than 0.1 day, or smoothing.

The underlying ejecta is assumed to be spherically symmetric, with the density described by a
broken power law that falls off like v^{-d} in the inner layers and more
steeply like v^{-10} in the outer layers. The transition between the power-laws
is set by the mass and kinetic energy.


The files under the "kilonova_models" directory are the original ones released with the Kasen+2017 paper

The files under the "systematic_kilonova_model_grid" are models calculated in the same way, but with a more
regular sampling of the grid of parameters: m, vk, Xlan


Filenames give

d    = exponent of inner denisty profile
n    = exponent of outer density profile
m    = ejeta mass in solar masses
vk   = "kinetic" velocity in units of c (defined by vk = (2 E/m)**0.5)
Xlan = mass fraction of lanthanides

Since the lanthanide species have so many lines,  Xlan largely sets the opacity of the ejecta
and controls how long lived and red the light curves are.

Light (or "weak" or "first peak") r-process material typically has Xlan ~< 1e-4
Heavy (or "strong" or "second and third peak") r-process material typically has Xlan >~ 1e-2

These files are in hdf5 format.  They are easy to read using
python and the h5py package (http://www.h5py.org/) and if you have hdf5
installed on your machine 

- The script readmodel.py shows how to read in the data.

- The script splot allows to pop up plots

Units of the spectra are ergs/sec/Hz
 - divide by 4piD^2 to get an observed flux (ergs/sec/Hz/cm^2)

(If you are having difficulty with hdf5 files, let me know and I can provide ascii files)







