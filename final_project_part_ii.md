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



[Return to portfolio homepage](https://nannunz.github.io/gis-portfolio/)
