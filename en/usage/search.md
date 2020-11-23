# Search

To take advantage of Isogeo search engine (based on contextual filters) and also on performances issues, search is a 2-steps process:

1. user enter a semantic search and/or pick one and/or many filters to reduce the results count,
2. user display filtered results then use capabilities available in the results list.

Note that user can display results list withtout any filter:

!["Search form without any filter"](/assets/ui_tabs_main_search_empty_en.png)

## Semantic search {#search-terms}

The search bar is the first widget at the top left of the plugin window.

Metadata fields where terms are searched:: 
- title
- filename or table name
- abstract
- keywords
- INSPIRE themes

To know more about how does the Isogeo search engine works, [read the official online documentation](https://help.isogeo.com/en/features/inventory/search.html).

---

## Contextual filters {#filters}

### Keyword filter {#keywords}

To filter by keywords, check one or more in the dedicated drop-down list:

!["Keyword dropdown filter"](/assets/search_options_keywords_en.png)

### Geographic filter {#geometric}

To filter results on a geographical bounding box, pick a modality from the drop-down list.
It's possible to filter on:

- map canvas bounding box
- convex hull stored from an active layers

!["Geographic filter - From an active layer"](/assets/search_options_geographic_en.png)

By default, the geographical filter give all data which intersect with the bounding box selected.
To change this behavior, choose a different operator in "Settings" tab, and then restart the search.

!["Set geometric operator for geographic filter"](/assets/settings_geographic_en.png)

### Other filters {#others}

All others filters are operating the same way, selecting a value will update all other dropdown lists:

!["Advanced search - all filters"](/assets/search_options_filters_en.png)

---

## Display and explore results {#display}

When a search is made (search terms or filter used), the number of results is updated and displayed in the orange button.

!["Results count on the display button"](/assets/search_results_show_en.png)

Clicking on this button displays search results in the table, 15 per 15 (pagination).

For each result, are displayed:

- the metadata title
- the last data update
- the geometry type
- available options to adda data to the map canvas (see below)

Two buttons allow navigation between different pages:

!["Results pagination"](/assets/search_results_pagination_en.png)

### Order results {#order}

Once displayed, results can be ordered.

By default, results are ordered according to a relevance rank. Obviously, when there is not text in the search bar, the relevance is the same for all results which are ordered by descending metadata creation date.

Others order options available:

- Alphabetical
- Metadata creation
- Metadata last update
- Data creation
- Data last update
