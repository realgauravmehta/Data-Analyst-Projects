# A list of all the changes made to these datasets. 

#### NYC Tree Census (2015)
After downloading this dataset, I deleted the following columns to reduce file size from 236MB to less than 100 MB. 

`[ 'created_at', 'block_id', 'the_geom', 'stump_diam', 'curb_loc', 'steward', 'guards', 'sidewalk', 'user_type', 'problems', 'root_stone', 'root_grate', 'root_other', 'trnk_wire', 'trnk_light', 'trnk_other', 'brnch_ligh', 'brnch_shoe', 'brnch_othe', 'zip_city', 'borocode', 'cb_num','cncldist', 'st_assem', 'st_senate', 'nta',  'boro_ct','x_sp', 'y_sp']`

#### Tree Species
I pulled this source from [a Wikipedia list](https://en.wikipedia.org/wiki/List_of_tree_species_in_New_York_City) and made no changes. The orginial dataset includes photos, and mine does not. 

#### NYC Income (2015)
I made a [custom query of all NYC zip codes](https://data.census.gov/cedsci/table?t=Income%20and%20Poverty&g=0500000US36005%248600000,36047%248600000,36061%248600000,36081%248600000,36085%248600000&tid=ACSST5Y2015.S1901) using the United States Census Bureau website. Several changes were made to this data after downloading from the original source to make the file smaller and more manageable in Tableau. I deleted all columns except a geographic identifier, zip code, and 6 income-related fields: mean, median and total household income estimates, and margin of error for each income estimate. I also cleaned the data: removed the string `ZCTA5` from all zip code fields, removed stray characters like "+" and "!", and replaced Census Bureau abbreviations in the first row with more readable column names. 

#### Rotten Tomatoes
No changes were made to this data after downloading from the original source.

#### Significant Volcanoes
No changes were made to this data after downloading from the original source.

#### FAA Wildlife Strikes
After downloading from the original source, I modified the `Airport Code` field to remove the "K" (i.e. changing codes from "KLGA" to "LGA") -- this allowed me to join this dataset to the Passenger Count dataset on the `IATA code` field. When aggregating by year in Tableau, I filtered out the 2015 data as it contained records from only the first half of that year. 

#### Passenger Counts (2014)
I pulled this list from a [Wikipedia source](https://en.wikipedia.org/wiki/List_of_busiest_airports_by_passenger_traffic_(2010–2015)) and filtered on US airports. I further cut several US airports that were on the list but did not have passenger counts, bringing the full list from 64 to 58 airports.
