## Predicting Evictions in New York City 

New York City is one of the most socioeconomically stratified and geographically segregated cities in the United States. As such, it is not uncommon for more vulnerable populations, such as low income communities or communities of color, to find themselves at the mercy of those with greater access to resources and power in our city – there is no clearer example than in New York City’s countless evictions and failure to provide accessible and affordable housing.

By building this model, my hope was to better understand both the factors that fuel evictions and to provide targeted support to individuals in these vulnerable areas. This model can be thought of as a basic template that can be customized based on the availability of data and the unique factors of each city or town. As this was an exercise in experimentation, my regression equation was relatively simple: 

Number of evictions_i= β_0 + β_1(Proportion of Black Residents)+ β_2(Median Income)+ β_3(Proportion of Evictions by ZIP Code)


## Data Sources 

<iframe title="NYC Data Sources" aria-label="Table" id="datawrapper-chart-V5u88" src="https://datawrapper.dwcdn.net/V5u88/1/" scrolling="no" frameborder="0" style="border: none;" width="600" height="531"></iframe>

Much of the data used for this model was sourced from the U.S. Census Bureau’s 2020 Census and the City of New York’s open data repository. Unlike many other metropolitan areas in the United States, New York makes a significant amount of data available for use by the public – including information on evictions, youth programs, and even a “Squirrel Census.” While the data do have significant gaps, including datasets where entire neighborhoods or ZIP codes are missing, the accessibility and variety of information here far exceeds that of nearly every other American city. 

## Walking Through the Process 

It is worth noting that the model in its current iteration is not perfect – while it does run, it generates a few errors that I have not been able to rectify at the time of writing this report. However, this has been an excellent educational experience and I can confidently share several cautionary tales for those trying to build similar models for their respective cities. 

## Step 1: Obtaining, Cleaning, and Preparing the Data
First, I obtained shapefiles from NYC’s data repository outlining the five boroughs, the neighborhood boundaries within each borough, and the outline for each ZIP code. In order to obtain more granular data for analysis, I downloaded both the TIGER shapefiles from the U.S. Census Bureau alongside data on demographics, income, and other housing characteristics by Census Tract. All datasets were given a preliminary cleaning in Python and exported as Excel files before being uploaded to GIS, where relevant columns were converted into compatible data types for future joins. 

Next, I cleaned and imported New York City’s eviction data. This dataset provides the date and address of each eviction filing in New York for the past few years, which provided me the opportunity to geocode each location and get a better sense of the spread of evictions throughout the city. Unfortunately, it was impossible to glean any geospatial insights from this point layer because there had been so many evictions it was difficult to tell where, exactly, they were concentrated. Using this point layer, I summarized the number of evictions by ZIP code after joining it to the neighborhood shapefile. I similarly summarized the demographic and income data from the Census to prepare it for the model. 

## Step 2: Try, and Fail, to Test a Basic Training Model. Realize, for the First Time, the Limitations of Your Data

<img src="https://github.com/nannunz/gis-portfolio/blob/main/classification%20fail.png?raw=true">

Falling victim to my own hubris, I assumed that the prepared data would simply allow me to “plug and play” when developing a Forest-Based Classification and Regression Model. This assumption would prove to be incorrect for two reasons: (1) All the information needed to be stored in the same feature class or table, as the model is incapable of pulling from multiple classes, and (2) If there are any null values in your data, regardless of whether or not you are using that variable in your model, the model will not run. 

Unfortunately, ArcGIS does not necessarily provide a simple or straightforward way to clear all null values. A find and replace approach requires the user to sort through each individual column – which, unfortunately, would be quite difficult with the number of columns I had hoped to incorporate in the model. One could simply select and delete rows containing null values, but this would likely skew our results significantly and exclude numerous ZIP codes from our analysis. Ultimately, the most sensible approach was to export the data from ArcGIS to Excel (using the Feature Class to Excel tool) and quickly calculate the average value for each column containing null values and replace those values with the average. Though not an ideal approach, replacing null values with the average prevents the data from becoming too skewed, which is what would happen if we were to replace those nulls with zeroes instead. 

After manually cleaning the data, it was imported back into ArcGIS and joined with the shapefile. It was then that I noticed something unusual: after multiple joins, there appeared to be duplicate rows despite ZIP codes matching perfectly in all tables pre-join. This turned out to be an unusual quirk of the way ZIP codes are laid out in New York City: some ZIP codes span multiple boroughs, and were thus spanning multiple rows where the demographic information matched, but the boroughs were logged differently. I used the summary statistics tool and remove identical features tool to ensure we were not double-counting certain areas. 

## Step 3: Try, and Fail, to Create a Proximity-Based Analysis. Realize, for the Second Time, the Limitations of Your Data

I had assumed that proximity to other evictions may be indicative of the likelihood of evictions occurring for a specific building or neighborhood. I attempted two analyses that would help quantify where evictions were most frequent: (1) A hot spot analysis and (2) Utilizing a radial basis function to weigh high-eviction areas more heavily. A radial basis function essentially creates a flat “sheet” to represent your geographic area, with each point on the sheet corresponding to a point on the map. For every input at a particular point – say, a documented eviction – the function raises the “sheet” in that particular point, ultimately creating a landscape where locations with a higher input count are “taller.” 

Unfortunately, as the datasets I was working with were relatively small, ArcGIS was unable to perform either analysis. In fact, I was so unsuccessful, that attempting to use the radial basis function prompted an error message to contact Esri support for additional assistance. 

<img src="https://github.com/nannunz/gis-portfolio/blob/main/radial%20basis%20fail.png?raw=true">

Rather than use a proximity based analysis, I ultimately decided to use the proportion of evictions to residents by ZIP code as my location-based variable in my model. 

<img src="https://github.com/nannunz/gis-portfolio/blob/main/Evictions%20by%20ZIP%20Code.png?raw=true">


## Step 4: Run the Model and Assess Preliminary Findings 

As mentioned at the beginning of this report, the model does run, nut it does unfortunately contain a few errors. This is likely due to the relatively small sample size available: I ultimately only had around 300 rows of data to feed the model, which severely limits its training ability. Nevertheless, I ran the model using 10,000 trees to see if we could glean any preliminary findings from what was available. 

<img src="https://github.com/nannunz/gis-portfolio/blob/main/ModelOutput.png?raw=true">

The model identified areas in the South Bronx and Eastern Brooklyn, such as Bedford-Stuyvesant, as being particularly high-risk areas for eviction. This finding is not terribly surprising based on the variables we have fed the model: while evictions are extremely common across the city (with the exception of Staten Island), these areas tend to have residents with the lowest incomes and large Black populations relative to other neighborhoods. 

<img src="https://github.com/nannunz/gis-portfolio/blob/main/BlackPop.png?raw=true">

<img src="https://github.com/nannunz/gis-portfolio/blob/main/MedianIncome.png?raw=true">

Areas of particular note include: Brownsville, East New York, Rugby-Remsen Village, Canarsie, Bedford-Stuyvesant, East Flatbush-Farragut, Bushwick, Mount Hope, Highbridge, East Tremont, and Concourse Village. I would therefore recommend that the Legal Aid Society, should they use this model to improve their outreach efforts, focus their energy on these areas. 




[Return to portfolio homepage](https://nannunz.github.io/gis-portfolio/)
