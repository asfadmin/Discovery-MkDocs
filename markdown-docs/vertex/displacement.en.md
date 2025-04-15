
# Displacement Portal

## What is the Displacement Portal?
The OPERA Surface Displacement (DISP) Products are Interferometric Synthetic Aperture Radar (InSAR)-derived displacement data made using a hybrid Persistent Scatterer (PS) and Distributed Scatterer (DS) time series processing approach. 
All displacement products are provided in the satellite’s line-of-sight (LOS) direction, meaning that surface movements are measured relative to the LOS, indicating whether a point is moving toward (positive value) or away (negative value) from the satellite. 
These products provide information on anthropogenic and natural movements of the Earth's surface, such as subsidence due to groundwater or oil and gas extraction, and ground motion from tectonic faults, landslides, volcanoes, and more. 
OPERA will be creating the products as soon as the input data acquired by the satellite becomes available. 
However, during the initial roll-out phase (ending end of 2025), the focus will lie on creating the historical data between 2016-2024. 
OPERA DISP products are derived from Sentinel-1A/B/C and NISAR satellite SAR data and cover North America.

The Displacement Portal provides the ability to visualize and interact with these products. 

The Displacement Portal is coming soon. Check back for more updates.

[add later]: <> (Access the [Displacement Portal](https://displacement.asf.alaska.edu/) to get started. Note that the Displacement Portal is also available by going to [Vertex](https://search.asf.alaska.edu), and selecting Displacement from the Search Type dropdown.)

## Beginning your Displacement Search
### Map Base Layers
The available base map layers can assist you in selecting your area of interest (AOI). 
In the top left corner of the map, you may click the checkbox to toggle your desired map layers on or off.

#### Basic Velocity
This layer shows the cumulative displacement over time (i.e., Velocity = total short-wavelength displacement / total time), derived using the short-wavelength displacement layer from the DISP-S1 product.
See the [FAQs](/datasets/disp_faq) for more details.
There are separate Ascending and Descending satellite path layers, and the layer will update to only display the correct direction based on your search filters.

### Selecting AOIs
When you first access the Displacement Portal, the point selector is active. You may click your desired point(s) on the map.
When you are done adding your Areas of Interest (AOIs), you can click the **Draw** toggle to stop drawing. You may click it again to select more AOIs on the map.

Once you have selected the AOI, the results panel will appear. The left panel lists your selected AOIs, labeled as **Series 1, Series 2**, and so on. A spinning loading icon will be displayed next to each series while it is loading.
The chart is displayed in the right panel. Currently, only time series values of short wavelength displacement may be displayed in the chart.

Each Series is color coded. Mousing over the AOI in the AOI list, on the chart, or on the map will highlight that AOI in all three locations.

## Interacting with Displacement Portal Results
### Area of Interest List

- Hovering over an AOI will highlight it on the AOI list, chart, and map.
- By default, all AOIs are shown on the chart. You may click the **checkbox** next to an AOI to toggle how it is displayed on the chart. When checked, AOIs will appear on the chart. When unchecked, they will appear as a grayed out series on the chart.
    - You may click the **All AOIs checkbox** to gray out all time series on the chart.
- You may click the **trash can** icon to delete an AOI from your list. This will remove it from the map, list, and chart.
- If you wish to delete all existing AOIs, you may click the **trash can** icon next to *All AOIs*. A confirmation message will be displayed. Clicking **Cancel** will not delete any AOIs. Clicking **Delete** will delete all existing AOIs from the map, list, and chart.


### Chart

- Hovering over a time series on the chart will highlight it in the AOI list, chart, and map. Hovering over individual points in the chart will provide additional information on that point.
- You may use the mouse to navigate the chart. There are **Zoom In** and **Zoom Out** buttons in the top right of the chart. The **Zoom to Fit** button will fit all time series into the visible chart.
- You may right-click any point in a time series to **Shift to Zero**.
- The **Date Slider** is below the chart. You may drag the pips to adjust the start and end dates.
- Click the **Export** icon in the top right to download a .csv file for all AOIs in your time series. *Note*: If an AOI is deselected in the AOI list it will not be included in the csv export.
- Click the **Settings** icon in the top right for additional options
    - Click the **Show Lines** checkbox to toggle lines on or off.
    - Click the **Show Linear Fit** checkbox to show the linear fit for each time series. The linear fit equations will be displayed above the chart. Dashed lines representing the linear fit will appear on the chart.
    - Click **Reset Chart Reference** to reset the chart to its original baseline reference.
  
### Flight Direction

In the header bar, click the **Flight Direction** button to change the flight direction. Changing the flight direction will update the chart, and all selected map layers. 
The flight direction options are Ascending (satellite heads from south to north) and Descending (satellite heads from north to south). 
Indicators displayed next to the Flight Direction show the satellite heading, radar look direction, and look angle range.
The indicators will update based on the selected direction.

### Additional Map Layers
In the top left corner of the map, there are additional map layers available. You may click the checkbox to select your desired layer. 

#### Rollout
This layer shows color-coded regional priorities for Displacement Product generation during the historical processing phase, which would initially include data from July 2016 to December 2024 and will be updated by the end of 2025. 
Regions are prioritized from 1 through 3, with 1 being the highest processing priority. 
Note that some sub-regions may be de-prioritized based on snow cover, vegetation, or other factors. 
There are separate Ascending and Descending variants, and the layer will update to display the correct direction based on your search filters.

### Search Tools
There are additional options available in the top right of the header bar.

- The **Share/Save** button opens the **Saved Searches** and **Share Search** menu. 
From **Saved Searches**, you can save or view a displacement search. You can also view your displacement search history. 
**Share Search** allows you to copy the current URL to share your search, or you may email the link.
- The **Info** button opens a modal with more information on the OPERA Surface Displacement Products (DISP).
- The **Help** icon opens the Vertex help menu, which includes video tutorials and documentation.
- The **language selector** enables you to switch languages. Currently, English and Spanish are available. 
- The **Sign In** icon displays the user options, including Saved Searches, Search History, Saved Filters, and Preferences. 

## Further Reading
[Displacement Products Roadmap](https://storymaps.arcgis.com/stories/9356add046654d719fcc20566fc1f243)

[Displacement Products Usage](/datasets/disp_usage)

[Displacement FAQs](/datasets/disp_faq)