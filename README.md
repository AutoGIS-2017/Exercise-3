# Exercise 3: Geocoding and spatial join

This week we will practice how to do geocoding and spatial joins in Geopandas. The overall aim this week is to make practical study to find out how many people live within 5 km (Euclidian) distance from big shopping centers in Helsinki Region. 

### Due dates
 
 - 100 % of point total if you return your solution within 1 week (due date 21.11.2016) 
 - 85 % of point total if your return your solution within 2 weeks (due date 28.11.2016)
   - Detailed hints provided
 - 50 % of point total if you return your solution within 3 weeks (due date 05.12.2016)
   - Full solution provided

## Sections

 - [Problem 1: Geocode shopping centers](#problem-1-geocode-shopping-centers)
 - [Problem 2: Create buffers around shopping centers](#problem-2-create-buffers-around-shopping-centers)
 - [Problem 3: How many people live within 5 km from shopping centers?](#problem-3-how-many-people-live-within-5-km-from-shopping-centers)

## Problem 1: Geocode shopping centers

In the first problem the aim is to find out the addresses of shopping centers and geocoding them as a single Shapefile called `shopping_centers.shp`.

1. From the internet find out the addresses for following shopping centers and write the addresses into a text file called `shopping_centers.txt`:

 - Itis
 - Forum
 - Iso-omena
 - Sello
 - Jumbo
 - Redi (i.e. use the metro station of Kalasatama)

Use same kind of formatting for the text file as in the [lesson materials](https://automating-gis-processes.github.io/2016/Lesson3-geocoding.html#geocoding-in-geopandas), thus use semicolon `;` as a separator and add a unique integer number as `id` (doesn't matter what) for each center. 

2. Geocode the addresses in Geopandas in a similar manner as was done in the [lesson materials](https://automating-gis-processes.github.io/2016/Lesson3-geocoding.html#geocoding-in-geopandas)

3. Make a Table join to retrieve the `id` column from original shopping centers DataFrame similarly as in [lesson materials](https://automating-gis-processes.github.io/2016/Lesson3-table-join.html)

4. Save the GeoDataFrame as a Shapefile called `shopping_centers.shp`

## Problem 2: Create buffers around shopping centers



## Problem 3: How many people live within 5 km from shopping centers?
