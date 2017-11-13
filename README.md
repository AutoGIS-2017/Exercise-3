# Exercise 3

This week we will practice how to do geocoding, spatial joins and nearest neighbour analysis in Geopandas. The overall aim this week is to make practical study to find out how many people live within 5 km (Euclidian) distance from big shopping centers in Helsinki Region, and which of those shopping centers is closest to your home and work location. 

- **Exercise 3 is due by the start of lecture on 20.11**.

- Don't forget to check out the [hints for this week's exercise](https://automating-gis-processes.github.io/2017/lessons/L3/exercise-3-hints.html) if you're having trouble.

- Scores on this exercise are out of **20 points**.

## Sections

 - [Problem 1: Geocode shopping centers](#problem-1-geocode-shopping-centers-5-points)
 - [Problem 2: Create buffers around shopping centers](#problem-2-create-buffers-around-shopping-centers-5-points)
 - [Problem 3: How many people live within 5 km from shopping centers?](#problem-3-how-many-people-live-within-5-km-from-shopping-centers-5-points)
 - [Problem 4: What is the closest shopping center from your home / work?](#problem-4-what-is-the-closest-shopping-center-from-your-home--work-5-points)
 - [Answers](#answers)
 
You can write all your codes into the same script called `spatial_queries.py`. If you want, you can also write your codes to multiple scripts, but remember then to name and comment your codes well with docstrings explaining which script belongs to which problem!
 
## Problem 1: Geocode shopping centers (5 points)

In the first problem the aim is to find out the addresses of shopping centers and geocoding them as a single Shapefile called `shopping_centers.shp`.

**Steps**

- From the internet find out the addresses for following shopping centers and write the addresses into a text file called `shopping_centers.txt`:

 - Itis
 - Forum
 - Iso-omena
 - Sello
 - Jumbo
 - REDI (i.e. use the metro station of Kalasatama)

Use same kind of formatting for the text file as in the [lesson materials](https://automating-gis-processes.github.io/2017/lessons/L3/geocoding.html#geocoding-in-geopandas), thus use semicolon `;` as a separator and add a unique integer number as `id` (doesn't matter what) for each center. 

- Geocode the addresses in Geopandas in a similar manner as was done in the [lesson materials](https://automating-gis-processes.github.io/2016/Lesson3-geocoding.html#geocoding-in-geopandas)

- Reproject the geometries into a EPSG projection 3879 similarly as in [lesson materials](https://automating-gis-processes.github.io/2016/Lesson3-projections.html#projections-converting-from-projection-to-another)
  
   - **Notice**: you need to pass the coordinate information as a proj 4 dictionary in a similar manner as in the lesson materials (see the second last bullet point in the [lesson materials](https://automating-gis-processes.github.io/2016/Lesson3-projections.html#projections-converting-from-projection-to-another)

- Make a Table join to retrieve the `id` column from original shopping centers DataFrame similarly as in [lesson materials](https://automating-gis-processes.github.io/2016/Lesson3-table-join.html)

- Save the GeoDataFrame as a Shapefile called `shopping_centers.shp`

## Problem 2: Create buffers around shopping centers (5 points)

Let's continue with our case study and calculate a 5 km `buffer` around the points. 

**Steps**

- Create a new column called `buffer` to your shopping-centers GeoDataFrame (or whatever you call it)

- Iterate over the rows in your GeoDataFrame and update the `buffer` column with a 5 km buffer Polygon.
  
  - Use Shapely's [buffer](http://toblerity.org/shapely/manual.html#object.buffer) function to create it (see the link for details how to use it)
  - You only need to use the `distance` -parameter, don't care about the other parameters.
  
- Replace the values in `geometry` column with the values of `buffer` column

## Problem 3: How many people live within 5 km from shopping centers? (5 points)

Last step in our analysis is to make a spatial join between our point-buffer layer and the same population grid that was [used in the lesson materials](https://automating-gis-processes.github.io/2016/Lesson3-spatial-join.html#download-and-clean-the-data).

**Steps**

- Read and prepare the population grid into a GeoDataFrame similarly as in [the lesson materials](https://automating-gis-processes.github.io/2016/Lesson3-spatial-join.html#download-and-clean-the-data)

- Make a spatial join between your buffered point layer and population grid layer

  - Note: Join the information now from buffer layer **into the population grid layer**

- Group the joined layer by shopping center index

- Calculate the sum of population living within 5 km for each shopping center.
  
  - Write the answers down here into the [Answers](#answers) section
  
## Problem 4: What is the closest shopping center from your home / work? (5 points)

In the last problem you should find out the closest shopping center from a) your home and b) work locations. 

**Steps**:

 - Create a txt-file called `activity_locations.txt` (use same formatting as in Problem 1) with two columns:
    - id --> unique number (e.g. 0 and 1)
    - addr --> address of your work and home (you don't need to reveal your home / work if you don't want to, these can be whatever two addresses from Helsinki!)
    
 - Read those addresses into Pandas and convert the addresses to Point objects using the geocoding functionalities of Geopandas
 - Find out the nearest shopping center to these points using the techniques shown during the lesson. You can use the shopping center addresses you geocoded in Problem 1.  

## Answers

Write the amount of population living within 5km from each shopping center:

 - Itis:
 - Forum:
 - Iso-omena:
 - Sello:
 - Jumbo:
 - REDI:


