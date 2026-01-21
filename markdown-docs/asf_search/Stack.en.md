# Stack

## Description

This class creates stacks of `Pair`s of `ASFProduct`s. A `Stack` contains 4+ lists of `Pair`s, which are described in the Attributes section below.

`Stack` is a supportive class for the soon-to-be-released `SBASNetwork` class, which will simplify and automate the creation of connected, multi-annual, seasonal SBAS stacks.
***

## Attributes
- `geo_reference` ASFProduct: A geographic reference scene from which to build a geographically collocated `Stack`.
- `opts` ASFSearchOptions: Search options used when searching products to create scene `Pair`s.
- `full_stack` List[Pair]: A list of every possible `Pair` in a `Stack`. This forms a complete network of `ASFProducts``.
- `remove_list` List[Pair]: A list of `Pair`s to remove from `full_stack` in order to create `subset_stack`
- `subset_stack` List[Pair]: The resulting list after removing the `Pair`s in `remove_list` from `full_stack`. This contains a possibly disconnected network of `ASFProducts`.
- `connected_substacks` List[List[Pair]]: A list of lists of Pairs. This contains each disconnected component of `subset_stack`. A length of 1 indicates that `subset_stack` represents a connected network of `ASFProducts`.

***

## Methods

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
