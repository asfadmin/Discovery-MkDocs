# Wildcard Queries

asf-search and SearchAPI support querying scene names via wildcards (* and ?) with the `granule_list` keyword and is also available on `dataset` search type in Vertex. This enables searching metadata embedded in scene names. Below are examples of useful queries with certain datasets.

## NISAR

NISAR data product names contain a few pieces of metadata that aren't directly searchable by additional attributes in CMR or aren't searchable params in asf-search

For a breakdown of NISAR data product naming conventions see: https://nisar-docs.asf.alaska.edu/naming-conventions/


### CRID Version Number
`CRID` version is available in CMR but isn't a searchable field in asf-search.

match all Level 2 NISAR products with CRID version X05010:

- `NISAR_L2_*X05010*`

match all NISAR science products with CRID version X05010 and above:

- `NISAR_L?_*X0501?*`

match all NISAR products with CRID version P05012 and above:

- `NISAR_*P05012*`

### Freq A & B Polarizations
While asf-search provides searching on these `mainBandPolarization` and `sideBandPolarization` fields you can't search strictly exclusively on single band data without getting possibly getting both bands in results. Data products denote when a band isn't used with `NA`.

Data products that strictly contain frequency A HH data 

- `NISAR_L?_\*_SHNA\*`

### Stack ids

Stack IDs are useful for building timeseries
`stack_id`: `RelativeOrbit_OrbitDirection_FrameNumber`

`NISAR_\*165_D_100\*`:
    
    * Relative Orbit: 165
    * Orbit Direction: D (Descending)
    * Frame Number: 100

Here is how to use the above pattern in asf-search to get adjacent NISAR timeseries results.
```python
import asf_search as asf

# Two adjacent stacks
stack_ids = ['165_D_100', '165_D_101']

multi_stack_results = asf.search(
    dataset=asf.DATASET.NISAR, 
    granule_list=[f'NISAR_*{stack_id}*' for stack_id in stack_ids]
    )

multi_stack_results.geojson()
```

## OPERA-S1

OPERA-S1 has a few useful fields not directly covered in places like Vertex but are possible in SearchAPI and asf-search.

Search for Level 2 OPERA products that use S1C as source acquisitions
`OPERA_L2_*S1C_*`

Vertex doesn't directly support searching on track number for OPERA-S1 data but users can use a pattern like `OPERA_L*-S1_T<Track ###>*` to limit to a specific track number.

The below pattern would return OPERA-S1 level 2 products with track number `95`:

- `OPERA_L2_*-S1_T095*`

OPERA Project spec pages are available here:
https://www.jpl.nasa.gov/go/opera/products/

<!-- ## UAVSAR
RPI docs: https://uavsar.jpl.nasa.gov/science/documents/rpi-format.html
POSLAR docs: https://uavsar.jpl.nasa.gov/science/documents/polsar-format.html
`Dthvly_34501_08038_006_080731_L090HH_XX_01.slc`

The first six character are an abbreviation for the desired target site (image may contain other sites).
`L090HH` is frequency band `L`, steering angle `090` followed by the polarization `HH`.
`XX` means there's no cross talk calibration  -->
