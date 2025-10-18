# Pair

## Description

This class describes a pair of ASFProducts. This is useful for, but not limited to, describing pairs of reference and seconary scenes for SAR interferometry. The class provides metadata describing the pair's temporal and perpendicular baselines. For Sentinel-1, an optional method is available that estimates temporal coherence.

`Pair` is a supportive class for the soon-to-be-released `Stack` and `SBAS` classes, which will simplify and automate the creation of fully connected, multi-annual, seasonal SBAS stacks.
***

## Attributes
- `ref_date` datetime.date: The acquisition date of the reference scene
- `sec_date` datetime.date: The acquisition date of the secondary scene
- `perpendicular` int: The pair's perpendicular baseline
- `temporal` datetime.timedelta: the pair's temporal baseline

***

## Methods

### <span style="color: #236192; font-size: 20px;">estimate_s1_mean_coherence()</span>

Estimates mean coherence for a Pair of Sentinel-1 scenes or bursts using the 11367x4367 overview of the 2019-2020 VV COH data from the Global Seasonal Sentinel-1 Interferometric Coherence and Backscatter Dataset: https://asf.alaska.edu/datasets/daac/global-seasonal-sentinel-1-interferometric-coherence-and-backscatter-dataset/

**args:**
None

**returns:**

- `float` describing the pair's estimated temporal coherence.

***
