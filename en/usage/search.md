# Search

To take advantage of Isogeo search engine (based on contextual filters) and also on performances issues, search is a 2-steps process:

1. user enter a semantic search and/or pick one and/or many filters to reduce the results count,
2. user display filtered results then use capabilities available in the results list.

Note that user can display results list withtout any filter:

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/ui_tabs_main_search_empty_en.png "Search form without any filter")

## Semantic search

The search bar is the first widget at the top left of the plugin window.

Metadata fields where terms are searched:: 
- title
- filename or table name
- abstract
- keywords
- INSPIRE themes

To know more about how does the Isogeo search engine works, [read the official online documentation](http://help.isogeo.com/en/features/inventory/search.html).

## Contextual filters

### Keyword filter

To filter by keywords, check one or more in the dedicated drop-down list:

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/search_options_keywords_en.png "Keyword dropdown filter")

### Geographic filter

To filter results on a geographical bounding box, pick a modality from the drop-down list.
It's possible to filter on:

- map canvas bounding box
- convex hull stored from an active layers

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/search_options_geographic_en.png "Geographic filter - From an active layer")

By default, the geographical filter give all data which intersect with the bounding box selected.
To change this behavior, choose a different operator in "Settings" tab, and then restart the search.

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/settings_geographic_en.png "Set geometric operator for geographic filter")

### Other filters 

All others filters are operating the same way. The only exception is the filter on the available actions that need to be checked.

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/search_options_actions_en.png "Filter on associated actions")

---

## Display and explore results

When a search is made (search terms or filter used), the number of results is updated and displayed in the orange button.

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/search_results_show_en.png "Results count on the display button")

Clicking on this button displays search results in the table, 15 per 15 (pagination).

For each result, are displayed:

- the metadata title
- the last data update
- the geometry type
- available options to adda data to the map canvas (see below)

Two buttons allow navigation between different pages:

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/search_results_pagination_en.png "Results pagination")

### Order results

Once displayed, results can be ordered.

By default, results are ordered according to a relevance rank. Obviously, when there is not text in the search bar, the relevance is the same for all results which are ordered by descending metadata creation date.

Others order options available:

- Alphabetical
- Metadata creation
- Metadata last update
- Data creation
- Data last update


