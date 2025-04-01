# Displacement Products Usage

## What are the Displacement Products?
The OPERA Surface Displacement (DISP) Products are Interferometric Synthetic Aperture Radar (InSAR)-derived displacement data with reduced decorrelation noise using a hybrid Persistent Scatterer (PS) and Distributed Scatterer (DS) time series processing approach. All displacement products are provided in the satellite’s line-of-sight (LOS) direction, meaning that surface movements are measured relative to the satellite, indicating whether a point is moving toward (positive value) or away (negative value) from the satellite. These products provide information on anthropogenic and natural movements of the Earth's surface, such as subsidence, tectonics, and landslides. The products will cover North America and be back-processed from 2016 for the Sentinel-1 mission. New products will be generated as Sentinel-1 data becomes available.

The Displacement Portal provides the ability to visualize and interact with these products.
[add later]: <> (Access the [Displacement Portal](https://displacement.asf.alaska.edu/) to get started. Note that the Displacement Portal is also available by going to [Vertex](https://search.asf.alaska.edu), and selecting Displacement from the Search Type dropdown.)

This provides some usage notes for these products.

## Data Interpretation Caution
Should data indicating ground movement on a house be a cause for concern?

InSAR detects small ground movements with millimeter-scale precision, but not all points indicate structural issues or land deformation. 
Many structures and surfaces move naturally due to environmental factors, affecting how radar signals are reflected. 
As an example, bridges expand and contract with temperature changes, which may be detected by InSAR but are not necessarily signs of structural damage. 
Since such movements are expected and accounted for in engineering and construction, InSAR data should always be analyzed alongside additional information and expert knowledge to distinguish natural behavior from potential issues affecting specific structures and infrastructure.

## Isolated Measurements and Outliers
InSAR ground motion measurements are based on reflected radar signals, which can originate from both the Earth's surface and human-made structures. 
Signal reflecting from these structures may be misinterpreted. For example, thermal expansion in buildings can appear as displacement, even though it does not indicate actual ground motion. 
Similarly, harvest cycles in crop fields can cause sudden changes in reflectivity, affecting displacement measurements.

DISP-S1 products mitigate outliers using masking thresholds that prioritize measurement point stability over time. 
However, pixels near masked regions may have borderline quality. 
For more reliable analysis, focus on clusters of points with consistent movement patterns rather than isolated points with unexpected motion.

## Area of interest vs pixel position
Each pixel shown in the map-view represents an area of 30m wide, and the height varies based on latitude.
The portal provides a point location when drawing a point interactively, but it is important to remember that the displacement data corresponds to the entire 30m x 30m in which the point is located. 
The recorded movements represent an aggregate of all surface changes within that pixel area rather than a precise measurement of a single point.
Also note that the mosaic pixels do not correspond 1-to-1 with the underlying data pixels, so it is possible click in two opposite corners of a mosaic pixel and get two different time series from two different underlying data pixels.
The mosaic is provided to highlight trends, and is not intended to be a rigorous data source for analysis.

## Contact
For any questions regarding the Displacement Portal, please contact ASF at uso@asf.alaska.edu.

For any questions or inquiries regarding the Displacement Products, please contact opera.sep@jpl.nasa.gov. 
