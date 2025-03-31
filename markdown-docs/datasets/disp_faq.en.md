# Displacement Products FAQs

**What datasets can be visualized in the Displacement Portal?**

The Displacement Portal displays the cumulative displacement and velocity (i.e averaged displacement over time) on a map. 
This information was derived from the “short_wavelength_displacement” layer found within each DISP-S1 dataset.

**What is “short-wavelength (i.e. local) displacement”?**

The short-wavelength displacement represents Earth’s surface ground movement observed in the satellite line-of-sight (LOS) with long-wavelength signals removed (i.e., >25 km) . 
This means that large-scale signals (such as atmospheric effects, plate motion, or large deformation signals) are filtered in order to highlight small-scale surface displacement. 
These data are provided as the “short_wavelength_displacement” layer within the DISP-S1 product package. 
The cumulative velocity map displayed is derived from this layer.

For the displacement measurement that includes both short- and long-wavelength signals, users are directed to look at the unfiltered “displacement” layer within the DISP-S1 product.
This may make large spatial features, such as Central Valley or Mexico City, look different in the portal.
The portal is meant to highlight local deformation and all signals should be retrievable from the unfiltered time series.

**How do I interpret deformation in the Displacement Portal?**

The high-pass filtering approach used to generate the “short-wavelength” layers is intended to highlight local deformation by removing long wavelength signals. 
Thus, large spatial features which exceed the filter kernel size of 25 km like large-scale subsidence in Central Valley, California and in Mexico City may look different than expected from an unfiltered time-series.

We have captured the effects of our filtering approach for simulations which approximate such large subsidence features in [this notebook](https://dolphin-insar--561.org.readthedocs.build/en/561/notebooks/demo-filtering-sizes/).
As an example, a simulated gaussian subsidence bowl may be filtered to appear as so, with subsidence flanked by vertical uplift:

![Screenshot](/images/gaussian_subsidence_example.png){: style="height:200px;width:450px"}

**What if I want to access the unfiltered displacement data?**

The unfiltered displacement datasets are available and can be downloaded as part of the OPERA-S1 dataset through [Vertex](https://search.asf.alaska.edu). 
Choose the DISP-S1 file type, and you will see the downloadable NetCDF file (with a “.nc” extension) available.
You must be signed into your Earthdata account to download these products.
Refer to the [Vertex User Guide](/vertex/manual/#vertex-getting-started-user-guide) for more information.

Note that the unfiltered displacement layer from the DISP-S1 product may not reflect what is visualized in the portal, since the portal only displays the short-wavelength layer.

**What are the data units in the Displacement Portal?**

Velocities plotted in map-view are in units of meters per year (m/yr) in the 1D line-of-sight direction.
The map overlay is colorized from -0.03 m/yr (blue) to +0.03 m/yr (red).

**How are the time series referenced in time and space?**

Each Displacement Product measures ground displacement relative to a specific reference date, which can change over time. 
The portal displays cumulative velocity from the first available date. 
Note, due to the short-wavelength filtering process, there is no local spatial reference point needed.

**How often are the data updated in the portal?**

New data is continuously being added to the archive and is immediately available for time series analysis.
However, the velocity mosaic is only updated weekly.

[//]: # (**Why are some points missing?**)

[//]: # ()
[//]: # (The OPERA team is revisiting their masking method as we speak, that was the reason for delaying the Product Validation Review meeting by a month. We can ask for an updated description from the science team via slack after they've implemented a new approach.)

[//]: # (In map-view: Points are masked if >10% of the datasets fail to meet a set of quality metrics, such as the level of temporal coherence, and phase similarity amongst neighboring pixels.)

[//]: # (Factors that may contribute to these quality metric issues may also include the presence of water bodies, ground motions that are too rapid to be resolved, and changes in surface characteristics &#40;e.g. vegetation loss/growth and/or snow/ice cover&#41;.)

[//]: # (In the time series plot: Masked pixels in the map-view are grayed out in the time series plot. )

**Why do I get an error message (e.g. “Timeseries Service Error”) when trying to plot data?**

These are the types of errors that will cause the "Timeseries Service Error" message:

- The selected area is outside the dataset coverage (e.g. over the ocean, over Europe, etc.)
- There is no data processed over the given frame yet. You can check the [rollout map layer](/vertex/displacement/#rollout) for more details.
- There is no valid data at the selected point. This happens when all short-wavelength displacement samples for the given AOI are pre-filtered by the dataset's validity mask.

**Are InSAR corrections applied to the time-series displayed in the portal?**

No. But InSAR corrections such as solid earth tides (SET) and ionospheric delay are added as separate layers in the DISP-S1 product. 
DEM errors can be corrected using the provided “perpendicular_baseline” layer. 
Tropospheric corrections will be available in the upcoming OPERA Level-4 Troposphere Zenith Radar Delays (TROPO) product. 
Refer to the DISP-S1 product specification document for additional details, and this Jupyter notebook on how to apply these corrections.

**Where is the product specification document?**

The dedicated DISP-S1 product page can be found [here](https://www.jpl.nasa.gov/go/opera/products/disp-product-suite/).