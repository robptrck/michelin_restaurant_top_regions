# michelin_restaurant_top_regions
Using DataGrip, Kaggle and Tableau to visualize the top regions for 3 star Michelin restaurants

## Steps Taken:

- Created a local db using SQLite in DataGrip.
- Downloaded 3 .csv files from Kaggle (2018-2019 michelin restaurant data separated by 1-2-3 stars).
- Created tables in DataGrip and imported .csv data.
    - This is where I encountered a problem. The dataset included zip codes, but some international zip codes were missing and others included integers and   characters. I had created a zip code column with type integer.

<img src="https://github.com/robptrck/michelin_restaurant_top_regions/blob/main/data_cleaning.png" width="300">

    - I removed the column as it wasn't necessary and included many nulls, but could have changed the data type to varchar.
- I had 3 separate .csv files for 1, 2, and 3 michelin star restuarants but wanted to combine them and manipulate them based on the number of stars they have, so I created a new column with the number of stars each restaurant had.

<img src="https://github.com/robptrck/michelin_restaurant_top_regions/blob/main/adding_missing_column.png" width="300">

- I used union_all to combine all 3 tables and created a new table with the result. I didn't use union because I wanted to include duplicates. The data spans 2018-2019 and it's possible a restaurants michelin rating would have changed in that time, but I'm not actually sure if union requires the entire row to be identical in order to be considered a duplicate. Going to research that!

union_all_create_new_table

<img src="https://github.com/robptrck/michelin_restaurant_top_regions/blob/main/union_all_create_new_table.png" width="300">

sql_ranking_query

<img src="https://github.com/robptrck/michelin_restaurant_top_regions/blob/main/sql_ranking_query.png" width="400">

sql_result

<img src="https://github.com/robptrck/michelin_restaurant_top_regions/blob/main/sql_result.png" width="400">

- Exported the data to an excel file and added it to Tableau Public

<img src="https://github.com/robptrck/michelin_restaurant_top_regions/blob/main/excel_export.png" width="300">

