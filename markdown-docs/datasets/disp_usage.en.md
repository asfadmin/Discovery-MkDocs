# Displacement Products Usage

##Displacement Product Considerations and Limitations
This provides some usage notes for the OPERA Displacement products. 
Access the [Displacement Portal](https://displacement.asf.alaska.edu/) to interact with these products, or see the [Displacement Portal documentation](/vertex/displacement) for more details on using the Portal.

***Caution on interpreting the data!***

## Should data indicating ground movement on a house be a cause for concern?

InSAR can detect small ground movements with millimeter-scale precision, but not all points indicate structural issues or land displacement. 
Many structures and surfaces move naturally due to environmental factors, affecting how radar signals are reflected. 
As an example, bridges expand and contract with temperature changes, which may be detected by InSAR but are not necessarily signs of structural damage. 
Since such movements are expected and accounted for in engineering and construction, InSAR data should always be analyzed alongside additional information and expert knowledge to distinguish natural behavior from potential issues affecting specific structures and infrastructure.

## Isolated Measurements and Outliers
InSAR ground motion measurements are based on reflected radar signals, which can originate from both the Earth's surface and human-made structures. 
Signal reflecting from structures may be misinterpreted. For example, thermal expansion in buildings can appear as displacement, even though it does not indicate actual ground motion. 
Similarly, harvest cycles in crop fields can cause sudden changes in reflectivity, affecting displacement measurements.

The Displacement Portal uses the Recommended Mask in the OPERA DISP products to reduce outliers. Pixels near masked areas might have lower quality. 
For more dependable analysis, prioritize groups of points showing similar movement over single points with unusual motion.

## What is the size of each pixel and how is displacement measured within that pixel?
Each pixel in the Basic Velocity map represents a 30m x 30m area. 
While you can select a point in the portal, the displayed displacement data is the average for that entire pixel. 
Therefore, recorded movements are an aggregate of all surface changes within the 30m x 30m area, not a precise point measurement. 
Additionally, the mosaic map pixels do not directly correspond to the underlying data pixels. 
Clicking in different corners of a single mosaic pixel can yield different time series from distinct underlying data pixels. 
The Basic Velocity mosaic serves to indicate trends and is not intended for rigorous analysis.

## Contact
For any questions regarding the Displacement Portal, please contact ASF at uso@asf.alaska.edu.

For any questions or inquiries regarding the Displacement Products, please contact opera.sep@jpl.nasa.gov. 
