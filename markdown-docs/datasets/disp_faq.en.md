# Displacement Products FAQs

**What datasets can be visualized in the Displacement Portal?**

The Displacement Portal displays the cumulative displacement and velocity (i.e., averaged displacement over time) on a map. 
This information was derived from the “short_wavelength_displacement” layer found within each OPERA DISP dataset.

**What is “short-wavelength (i.e., local) displacement”?**

The short-wavelength displacement represents ground movement measured in the satellite line-of-sight (LOS) with long-wavelength signals filtered, so it is a basic, uncalibrated displacement measurement. 
The product filters wavelengths >30 km . This means that large-scale signals, such as atmospheric effects, large-scale subsidence, and plate motion, are filtered in order to highlight local surface displacement. 
In some cases, the local displacement may have opposite LOS motion to the actual displacement due to filter effects (see the section “**How do I interpret displacement in the Portal**”). 
The “short_wavelength_displacement” layer comes with the DISP product package and is made for visualization purposes. 
This filtering approach also removes the need to select a local reference point (common for basic, uncalibrated InSAR displacements). 
The velocity maps and displacement time series displayed in the Displacement Portal are derived from this layer. 

For the displacement measurement that includes both short- and long-wavelength signals, users are directed to look at the “unfiltered” displacement layer within the DISP product.

In the future, the portal will host Ortho velocity maps derived from the upcoming OPERA Vertical Land Motion (VLM) product suite. 
Unlike the current Basic velocity maps which are computed in the satellite line-of-sight, the Ortho velocity maps will be computed for the vertical and east-west directions.

**How do I interpret displacement in the Portal?**

The filtering approach used to generate the “short-wavelength” layers is intended to highlight local displacement by removing long-wavelength signals. 
Large spatial features that exceed the filter kernel size of 30 km, such as subsidence in Central Valley, California and in Mexico City, are filtered to emphasize local displacement signals. 
These locations will look different than the unfiltered time-series in the product displacement layer.

Below we show synthetic examples of filtered and unfiltered displacement signals. 
The examples show that residual displacement patterns can emerge after filtering (see figure below).

More details can be found in this [notebook](https://dolphin-insar--561.org.readthedocs.build/en/561/notebooks/demo-filtering-sizes/).

![Screenshot](/images/disp_faq_1.png){: style="height:900px;width:700px"}

The figure above shows an example of the filtering approach (>30 km filter kernel) applied to a 65 km diameter subsidence bowl (left) and creeping right lateral transform fault (right). 
After the long-wavelength signal is filtered only the local displacement remains. The filtered subsidence bowl has apparent uplift along the edges. 
An analogous real-world example can be found in the Displacement Portal along the Central Valley in California. 
The filtered fault shows local displacement next to the fault and no displacement in the far field. 
An analogous real-world example can be found in the Displacement Portal along the Central San Andreas Fault near Parkfield, CA.

**What if I want to access the unfiltered displacement data?**

The unfiltered displacement datasets are available and can be downloaded as part of the OPERA-S1 dataset through [Vertex](https://search.asf.alaska.edu). 
Choose the DISP-S1 file type, and you will see the downloadable NetCDF file (with a “.nc” extension) available.
You must be signed into your Earthdata account to download these products.
Refer to the [Vertex User Guide](/vertex/manual/#vertex-getting-started-user-guide) for more information.

Note that the unfiltered displacement layer from the DISP product will not reflect what is visualized in the portal, since the portal only displays the short-wavelength layer.

**What are the data units in the Displacement Portal?**

Velocities plotted in map-view are in units of meters per year (m/yr) in the line-of-sight direction. 
The map overlay is colorized from -0.03 m/yr (blue) to +0.03 m/yr (red). 
Local displacement in the time series plot is in units of meters in the line-of-sight direction.

**How are the time series referenced in time and space?**

Each Displacement Product measures ground displacement relative to a specific reference date, which can change over time. 
The portal displays cumulative velocity and displacement from the first available date. 
Note, due to the short-wavelength filtering process, there is no local spatial reference point needed.

**How often are the data updated in the portal?**

New data is continuously being added to the archive and is immediately available for time series analysis.
The OPERA velocity measurements displayed in the portal are updated weekly.

**Why are some points missing?**

In map-view: Points are masked if any of the datasets fail to meet a set of quality metrics, such as level of temporal coherence and phase similarity amongst neighboring pixels. 
These quality metrics are captured in the Recommended Mask layer that can be downloaded with the Displacement product. 
Factors that may contribute to these quality metric issues may also include the presence of water bodies, ground motions that are too rapid to be resolved, and changes in surface characteristics (e.g. vegetation loss/growth and/or snow/ice cover).

In the time series plot: Masked pixels are not plotted.

**Why do I get an error message (e.g. “Timeseries Service Error”) when trying to plot data?**

These are the types of errors that will cause the "Timeseries Service Error" message:

- The selected area is outside the dataset coverage (e.g. over the ocean, over Europe, etc.)
- There is no data processed over the given frame yet. You can check the [rollout map layer](/vertex/displacement/#rollout) for more details.
- There is no valid data at the selected point. This happens when all short-wavelength displacement samples for the given AOI are pre-filtered by the dataset's validity mask.

**Are InSAR corrections applied to the time-series displayed in the portal?**

No. But InSAR corrections such as solid earth tides (SET) and ionospheric delay are added as separate layers in the DISP product and can be made outside of the portal. 
DEM errors can be corrected using the provided “perpendicular_baseline” layer. 
Tropospheric corrections will be available in the upcoming OPERA Level-4 Troposphere Zenith Radar Delays (TROPO) product. 
Refer to the DISP product specification document for additional details and this jupyter notebook on how to apply these corrections.

**Where is the product specification document?**

The dedicated DISP-S1 product page can be found [here](https://www.jpl.nasa.gov/go/opera/products/disp-product-suite/).