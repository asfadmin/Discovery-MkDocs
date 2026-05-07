# SBASNetwork

## Description

This class is a child of the `Stack` class. It is capable of creating seasonal SBAS networks, spanning multiple years and connected by bridge pairs.
***

## Attributes
- `geo_reference` ASFProduct:  A geographic reference scene from which to build a geographically collocated `SBASNetwork`. This will be `None` if an SBASNetwork is built using the `SBASNetwork.from_search_results` class method.  
- `opts` ASFSearchOptions: Search options in which an SBASNetwork's temporal and seasonal bounds are defined
- `_season` Tuple[int, int]: Julian days representing the start and end of valid season for seasonal filtering within the `SBASNetwork`.
- `_start` str: String timestamp for the start time of the temporal bounds of the `SBASNetwork`
- `_end` str: String timestamp for the end time of the temporal bounds of the `SBASNetwork`
- `perpendicular_baseline` int or float: The perpendicular baseline of the SBASNetwork in meters.
- `inseason_temporal_baseline` int: The temporal baseline of the `SBASNetwork`, not including longer temporal baselines of bridge pairs spanning one or more years.
- `bridge_target_date` str: The "%m-%d" formatted string of the date to target when building bridge pairs to connect a network with seasonal gaps. Valid birdge dates will be within `inseason_temporal_baseline`/2 days on either side of the `bridge_target_date`
- `bridge_year_threshold` int: The number of years bridge pairs are allowed to span.
- `allow_missing_state_vectors` bool: Determines whether an `SBASNetwork` may include `Pair`s containing SLCs with missing state vectors, which results in a `Pair.perpendicular baseline` value of None.
- `full_stack` List[Pair]: A list of every possible `Pair` in an `SBASNetwork`. This forms a complete network of `ASFProducts`.
- `remove_list` List[Pair]: A list of `Pair`s to remove from `full_stack` in order to create `subset_stack`
- `subset_stack` List[Pair]: The resulting list after removing the `Pair`s in `remove_list` from `full_stack`. This contains a possibly disconnected network of `ASFProducts`.
- `connected_substacks` List[List[Pair]]: A list of lists of Pairs. This contains each disconnected component of `subset_stack`. A length of 1 indicates that `subset_stack` represents a connected network of `ASFProducts`.
***

## Methods

### <span style="color: #236192; font-size: 20px;">from_search_results(cls, stack_search_results, perpendicular_baseline, inseason_temporal_baseline, bridge_year_threshold, bridge_target_date, opts, allow_missing_state_vectors)</span>

Alternate `SBASNetwork` constructor that allows for the creation of an `SBASNetwork` from the ASFSearchResults of a `baseline.stack` search instead of performing its own `baseline.stack` search on a geographic reference product.

**args:**
- `stack_search_results` ASFSearchResults: The `baseline.stack` ASFSearchResults from which to build the `SBASNetwork`.
- `perpendicular_baseline` int or float: The perpendicular baseline of the SBASNetwork in meters.
- `inseason_temporal_baseline` int: The temporal baseline of the `SBASNetwork`, not including longer temporal baselines of bridge pairs spanning one or more years.
- `bridge_year_threshold` int: The number of years bridge pairs are allowed to span.
- `bridge_target_date` str: The "%m-%d" formatted string of the date to target when building bridge pairs to connect a network with seasonal gaps. Valid birdge dates will be within `inseason_temporal_baseline`/2 days on either side of the `bridge_target_date`
- `opts` ASFSearchOptions: Search options in which an SBASNetwork's temporal and seasonal bounds are defined
- `allow_missing_state_vectors` bool: Determines whether an `SBASNetwork` may include `Pair`s containing SLCs with missing state vectors, which results in a `Pair.perpendicular baseline` value of None.
- `allow_missing_state_vectors` (optional) bool=False: Determines whether a `Stack` may include `Pair`s containing SLCs with missing state vectors, which results in a `Pair.perpendicular baseline` value of None.

**returns:**
- An `SBASNetwork` object

### <span style="color: #236192; font-size: 20px;">remove_pairs(self, pairs)</span>

Adds Pairs to `self.remove_list` and removes them from `self.subset_stack`.

**args:**
- `pairs` List[Pair]: A list of Pairs to remove from `self.subset_stack`

***

### <span style="color: #236192; font-size: 20px;">add_pairs(self, pairs)</span>

Adds `Pair`s to `self.subset_stack` and, if necessary, to `self.full_stack`.
I.e., remove `Pair`s from `self.remove_list` if present or else add them to `self.full_stack`. 

This allows for the addition of custom `Pair`s that were not originally present in `self.full_stack`.

**args:**
- `pairs`: A list of Pairs to add to `self.subset_stack` (and possibly `self.full_stack`)

***

### <span style="color: #236192; font-size: 20px;">get_scene_ids(self, pair_list)</span>

Provides scene names for all `ASFProducts` in a list of `Pairs`. This is useful when ordering pair-based products from ASF HyP3 or HyP3+ On-Demand Processing.

If no stack_dict is passed, `get_scene_ids()` defaults to using the largest connected substack in `connected_substacks`.

**args:**
- `pair_list` List[Pair]: A list of `Pair`s for which to retrieve scene IDs.

**returns:**
- A list tuples containing the reference and secondary scene names for each `Pair` in a `Pair` list.
***


### <span style="color: #236192; font-size: 20px;">plot(self, pair_list)</span>

Plots one or more pair_list member variables of an `SBASNetwork`: `full_stack`, `remove_list`, `subset_stack`, and/or `connected_substacks`.

**args:**
- pair_list List[Pair] or List[List[Pair]]: The pair list or list of pair lists to plot. Defaults to plotting all pair_lists within `connected_substacks`.
