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

<div class='tableauPlaceholder' id='viz1653184186730' style='position: relative'><noscript><a href='#'><img alt='Top 3 Michelin Star Restaurants (2018-2019) ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;To&#47;Top3MichelinStarRestaurants2018-2019&#47;Sheet1&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='Top3MichelinStarRestaurants2018-2019&#47;Sheet1' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;To&#47;Top3MichelinStarRestaurants2018-2019&#47;Sheet1&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /></object></div>                <script type='text/javascript'>                    var divElement = document.getElementById('viz1653184186730');                    var vizElement = divElement.getElementsByTagName('object')[0];                    vizElement.style.width='100%';vizElement.style.height=(divElement.offsetWidth*0.75)+'px';                    var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>
