
# Displacement Tool

## What is the Displacement Tool?
The OPERA Sentinel-1 Displacement Products are high-quality Interferometric Synthetic Aperture Radar (InSAR)-derived displacement data with reduced decorrelation noise using a hybrid Persistent Scatterer (PS) and Distributed Scatterer (DS) time series processing approach. These products provide information on anthropogenic and natural movements of the Earth's surface, such as subsidence, tectonics, and landslides. The products will cover North America and be back-processed through the start of the Sentinel-1 mission. New products will be generated as Sentinel-1 data becomes available.

The Displacement Tool provides the ability to visualize and interact with these products. 

The Displacement Tool is coming soon. Check back for more updates.

[add later]: <> (Go to [Displacement Tool](https://displacement.asf.alaska.edu/) to begin using the tool. Note that the Displacement Tool is also available by going to [Vertex](https://search.asf.alaska.edu), and selecting Displacement from the Search Type dropdown.)


## Beginning your Displacement Search
### Map Base Layers
The available base map layers can assist you in selecting your AOI. Displacement products are available in areas where Deformation or Velocity data is present.
In the top left corner of the map, you may click the checkbox to select your desired map layer.

#### Cumulative Velocity
This is a derived layer based on the cumulative deformation layer from the displacement products.
There are separate Ascending and Descending variants, and the layer will update to display the correct direction based on your search filters.

#### Cumulative Deformation
This layer is based on shortwave displacement.
There are separate Ascending and Descending variants, and the layer will update to display the correct direction based on your search filters.

### Selecting AOIs
When you first access the Displacement Tool, the point selector is active. You may click your desired point(s) on the map.
You may also click **Point** for a dropdown list. You may choose to draw a polygon, bounding box, or circle instead. When you are done adding your Areas of Interest (AOIs), click the **Draw** toggle to stop drawing. You may click it again to select more AOIs on the map.

Once you have selected an AOI, the results panel will appear. The left pane lists your selected AOIs, labeled as **Series 1, Series 2**, and so on. A spinning loading icon will be displayed next to each series while it is loading.
The chart is displayed in the right pane. If your AOI is a polygon, bounding box, or circle, the time series is an area average of all pixels within the AOI. Currently, only time series values of short wavelength displacement may be displayed in the chart.

Each Series is color coded. Mousing over the AOI in the AOI list, on the chart, or on the map will highlight that AOI in all three locations.

## Interacting with Displacement Tool Results
### AOI List

- Hovering over an AOI will highlight it on the AOI list, chart, and map.
- By default, all AOIs are shown on the chart. You may click the **checkbox** next to an AOI if you wish to hide it from the chart. When checked, AOIs will appear on the chart. When unchecked, they will appear as a grayed out series on the chart.
    - You may click the **All AOIs checkbox** to gray out all time series on the chart.
- You may click the **trash can** icon to delete an AOI from your list. This will remove it from the map, list, and chart.

### Chart

- Hovering over a time series on the chart will highlight it in the AOI list, chart, and map. Hovering over individual points in the chart will provide additional information on that point.
- You may use the mouse to navigate the chart. There are **Zoom In** and **Zoom Out** buttons in the top right of the chart. The **Zoom to Fit** button will fit all time series into the visible chart.
- You may right-click any point in a time series to **Set as Baseline**.
- The **Date Slider** is below the chart. You may drag the pips to adjust the start and end dates.
- Click the **Export** icon in the top right to download a csv for all AOIs in your time series. *Note*: If an AOI is deselected in the AOI list it will not be included in the csv export.
- Click the **Settings** icon in the top right for additional options
    - Click the **Show Lines** checkbox to toggle lines on or off.
    - Click the **Show Linear Fit** checkbox to show the linear fit for each time series. The linear fit equations will be displayed above the chart. Dashed lines representing the linear fit will appear on the chart.
    - Click **Reset Chart Reference** to reset the chart to its original baseline reference.
  
### Flight Direction

In the header bar, click the **Flight Direction** button to change the flight direction. Changing the flight direction will update the chart, and all selected map layers.

### Additional Map Layers
In the top left corner of the map, there are additional map layers available. You may click the checkbox to select your desired layer. 

#### Rollout
This layer provides color-coded priority for Displacement Products creation by region.
Regions are prioritized 1 through 3, with 1 being the highest processing priority.
Note that some sub-regions may be de-prioritized based on snow cover, vegetation, or other factors.
There are separate Ascending and Descending variants, and the layer will update to display the correct direction based on your search filters.

### Search Tools
There are additional options available in the top right of the header bar.

- The **Share/Save** button opens the **Saved Searches** and **Share Search** menu. 
From **Saved Searches**, you can save or view a displacement search. You can also view your displacement search history. 
**Share Search** allows you to copy the current URL to share your search, or you may email the link.
- **Info** opens a modal with more information on the OPERA Sentinel-1 Displacement Products.
- **Help** opens the Vertex help menu, which includes video tutorials and documentation.
- The **language selector** enables you to switch languages. Currently, English and Spanish are available. 
- The **Sign In** icon displays the user options, including Saved Searches, Search History, Saved Filters, and Preferences. 

## Further Reading
[Displacement Products Roadmap](https://storymaps.arcgis.com/stories/9356add046654d719fcc20566fc1f243)
