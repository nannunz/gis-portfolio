## Building an Eviction Model for Atlanta

## Overview of the Issue and Product
For this project, I would like to develop a housing vulnerability prediction model for the Metro Atlanta area, which includes Fulton, DeKalb, Gwinnett, Clayton, and Cobb counties. Through my capstone project, which takes a quantitative and qualitative approach to measuring the impact of COVID-19 on Atlanta and its recovery, access to affordable housing has come up time and time again as one of the city’s most pressing issues. While the eviction moratoriums may have provided temporary relief, both the city and the metro area at large have experienced rapid gentrification fueled by an influx of residents from other cities looking to buy cheaper homes and, more significantly, the expansion of major universities in the city: Georgia Institute of Technology, Georgia State University, Clark Atlanta University, Spelman College, and Moorehouse College.  

Gentrification is also being fueled beyond Atlanta’s borders. There are numerous attempts by private actors to predict housing values and foreclosures, such as Zillow or BlackRock, who are then able to then purchase these homes at a lower value and flip them for a significantly higher selling price. At this time, there does not appear to be a similar model utilized by the public sector to facilitate policy interventions. What I hope to do with this model is evaluate Census tracts and neighborhoods at high-risk for eviction based on various indicators, including: demographic information, rate of eviction filings, rate of foreclosure, average home value, and the proportion of renters and buyers. Once high-risk areas are identified, residents can be targeted for specific policy interventions that produce more stable housing, such as access to legal aid or rental assistance.

The product itself will be a prediction model developed in ArcGIS pro and an online map or storyboard documenting the process of developing the model, connecting data sources (such as public APIs) to the tool, and maps highlighting the most vulnerable areas. 


## Client and Beneficiaries
The model would be used by the Georgia Department of Community Affairs (DCA), which was founded with the goal of creating affordable housing.   The core tenants of the DCA have since expanded to include: “safe and affordable housing, local government assistance, and community and economic development” – in short, they hope to “build strong, vibrant communities” within the state of Georgia.  The DCA is in a unique position of being community-focused, but also having the authority to execute policy ideas and provide financial support, rather than having to lobby an external organization to intervene in the way many nonprofits or mutual aid organizations do. 

Ideally, not only would the DCA benefit from having this tool, but low-income Atlanta families would feel the benefits most acutely. Though they may not be the primary client, I would hope to make the tool accessible for use by Atlanta residents and housing nonprofits so that the burden of utilizing the information does not fall solely onto the DCA, a relatively underfunded agency. As such, the product will need to be relatively easy to use, simple to update, and inexpensive to maintain. 

## Available Data:
<iframe title="Atlanta Data Sources" aria-label="Table" id="datawrapper-chart-tk6QH" src="https://datawrapper.dwcdn.net/tk6QH/1/" scrolling="no" frameborder="0" style="border: none;" width="600" height="960"></iframe>

## Concerns and Potential Pitfalls: 
There are several concerns about the feasibility of building this model, the most pressing of which is the need to draw data from a wide variety of sources. Unlike cities like New York or San Francisco, Atlanta does not provide large, robust, open data with which to analyze the goings-on of the city. While there are local attempts to track this information from organizations like Data Nexus or the Atlanta Regional Commission, additional information will need to be pulled from sources external to the city, such as the Census Bureau or Zillow. 

While the predictive model will be the primary product, there are several smaller steps that might be more feasible to implement for the scope of this project and the data available. Two features I would like to create are: a step-by-step instructional guide for integrating Zillow’s API into ArcGIS Pro and the automation of basic statistical functions using Python. While I may not be able to build out the full model, creating a foundation for basic geospatial analysis certainly seems feasible. 

[Return to portfolio homepage](https://nannunz.github.io/gis-portfolio/)
