# <center> Predicting Housing Prices in Ames, Iowa, using Multiple Linear Regression

# Background:

Commercial real estate search companies such as [Zillow](https://www.zillow.com/) and [RedFin](https://www.redfin.com/) provide the ability to find the housing options that match their prospective buyers' needs. For instance, Zillow allows its subscribers to find key information on several properties in a geographic area including `final sales price`, `square footage`, `number of bedrooms`, `number of bathrooms`, and `the property's address`. Zillow uses individual home features to calculate its proprietary [Zestimate](https://www.zillow.com/z/zestimate/) or its estimate of a houses market value.

# Problem Statement:

`MyHomeSearch` is an emerging competitor to Zillow and RedFin in the real estate search engine industry. As it is considering differentiating factors from these large competitors, it has contracted data analytics services to:

* Identify home features that are relevant in predicting home sale prices that Zillow and RedFin do not currently display.
* Create a linear regression model that will predict home sale prices based on observable features for houses not yet listed in these websites.

`MyHomeSearch` expects to access home features data that is not yet available to the competition. These objectives will help `MyHomeSearch` make the choice whether to invest in modifying its current home search profiles with additional features and whether it should invest in purchasing the additional data to offer more search options to its current and future subscribers. The results of this analysis will be presented to `MyHomeSearch's` Chief Executive and Chief Information Officers.

A typical Zillow profile such as the one below includes features such as:
* Sale Price
* Number of bedrooms
* Number of bathrooms
* Total square footage
* Date of sale
* Zestimate
* Estimated refinance payment
* Home type
* Year built
* Type of cooling system
* Number of parking spaces
* Lot size in square feet
* Type of heating system
* Basement area
* Type of basement (i.e., partially finished, rear entrance)
* Flooring type
* Appliances available
* Total interior livable area
* Finished area above and below ground
* Total number of fireplaces
* Number of levels
* Fence type
* Architectural style
* Construction materials
* Property condition
* Whether the property is a new construction
* Utilities/ Green energy information
* Price history
* The same features for neighboring houses

<div>
<img src="https://wp-tid.zillowstatic.com/8/real-estate-facebook-ad-example-carousel-dd4184-941x1024.png" alt="drawing" style="width:600px;"/>
  
# Data Sources:

Using data from the city of Ames', Iowa, Assessor's Office for individual residential properties sold between 2006 to 2010, additional features that have an important relationship to sales price and that are not yet listed in Zillow profiles will be investigated. These data will also be used to build a machine learning model to predict sales price based on observable features. The dataset consists of 2,929 observations with 82 home features. The data set includes 23 nominal features, 23 ordinal features, 14 discrete features, and 20 continuous features and two identifying variables. A data dictionary can be found in [this](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt) document and source.

The following data dictionary provides more a description of the features used in the prediction of house sale prices.

|Feature name |Description|
|:---|:---|
|`high_bsmt_qual`|A binary variable for whether the height of the basement is 90 inches or higher|
|`high_heating_qc`|A binary variable for whether the quality and condition of the house was good or excellent|
|`year_built`|Year the house was built|
|`glq_alp_bsmt_sf`|Whether the finished area in square feet of the basement is considered good or average living quarter|
|`bsmt_exposure`|Basement exposure to walkout or garden level walls|
|`good_condition`|Whether the house is in good, very good, excellent, or very excellent condition|
|`masonry_brickstone`|Whether the masonry veneer type is made of stone or brick face|
|`bathroom_in_bsmt` |Whether there is at least one full bathroom in the basement|
|`garage_area`|Garage size in square feet|
|`lot_area`|Lot size in square feet|
|`gr_liv_area`|Above grade living area in square feet|
|`vibyl_siding_ext_1` |Whether the exterior covering on the house is made of Vynil Siding|
|`foundation_poured_concrete`|Whether the foundation is made of `poured concrete`|
|`garage_finished_or_roughly`|Whether the garage is finished or roughly finished|
|`garage_is_attached`|`1` if garage is attached to the house, `0` if not|
|`total_bsmt_sf`|Total square feet of basement|
|`high_qual`|Whether the overall material and finish of the house is good, very good, excellent, or very excellent|
|`popular_nghood`|Whether the house is located in these neighborhoods: `NAmes`,`CollgCr`,`OldTown`,`Edwards`,`Somerst`|
|`mas_vnr_area`|Masonry veneer area in square feet|
|`1st_flr_sf`|First floor square feet|
|`totrms_abvgrd`|Total rooms above grade|
|`full_bath`|Number of bathrooms|
|`year_remod/add`|Remodel date|
|`good_or_excellent_kitchen`|Whether the kitcken quality is rated as `Good` or `Excellent`|
|`fireplaces`|Number of fireplaces|
|`kitchen_abvgr`|Number of kitchens above grade level|
|`high_exter_qual`|Whether the quality of the material on the exterior of the house is `Excellent` or `Good`|
|`high_fireplace_quality`|Whether the quality of the fireplaces is `Excellent` or `Good`|

# Methodology:

To analyze the data and achieve the project goals, the following steps will be used:

### Identifying features that `MyHomeSearch` should consider for displaying on its home profiles:
1. Ingest and clean the data set.
2. Explore the relationship of all features in the data set to the target feature, or sale price.
3. Use a multiple linear regression model and data visualization to determine which features `MyHomeSearch` should consider for presentation on its website.
4. Narrow down a list of features for inclusion in a machine learning model to predict sale price.

### Developing a machine learning model to predict sale price:
1. Run a linear regression model on a train, test split of the train data set.
2. Evaluate the performance of the model using metrics such as r-squared and mean squared error. Evaluate the performance against the null model.
3. Implement Ridge and Lasso regularization applying grid search to find the optimal hyperparameters that will produce the best model performance on the testing data set.
4. Once a final model is selected, apply the data cleaning steps from the first objective to the testing data set, generate predictions on the testing data set and load them to Kaggle for evaluation of the performance of the model.

# Conclusions and Recommendations:

Through a multiple linear regression model, a machine learning algorithm was used to predict home prices using data from the city of Ames, Iowa. Over 80 features about the homes sold between 2006 and 2010 were considered as potential predictors of home sale prices. `MyHomeSearch` requested data analytics services to understand if any of those features predicted home sale prices and if any of those features are not currently being displayed by Zillow and other large competitors in the real estate online search industry. In addition, `MyHomeSearch` also set out to understand if it could predict home prices accurately in the event that additional data of home features became available in regions where competitors don't have a large presence in terms of the number of houses with actual or predicted prices.

This analysis concluded the following features had statistically significant effect on home prices at the 0.05 significance level:
* Year Built
* Living area in square feet
* Qualitative ratings on overall material and condition of the house
* Qualitative ratings on fireplace and heating quality and condition
* Size of the garage in square feet
* Materials used in exterior of the house
* Year when the house was last remodeled
* Having at least one bathroom in the basement
* Number of fireplaces
* Fireplace quality
* Number of bathrooms
* Number of bedrooms

Zillow already displays some of these features on its online profiles. However, it does not have subject matter expert's feedback on home quality and conditions. For instance, Zillow only provides an indicator of the condition of the house but does not provide detailed information about assessor's ratings on material and finish for a house. Additional qualitative information such as whether a house has good or excellent fireplace quality and heating quality and condition as well as the materials involved in the construction of the house, such as in its foundation, could be distinguishing pieces of information that `MyHomeSearch` could provide to home searchers or investors who would like to know more detail about their prospective homes. A potential niche market of clients who would be interested in these data are real estate investors interested in finding properties in less than optimal condition to transform them into profitable properties.

A machine learning algorithm based on a ridge regression model that explained predicted around 87.3% of the variance in the sales prices of unknown homes to the model. On average, the actual and predicted price followed one another, although at both the low and high ends of the distribution of sales price, the model performed less optimally. More research is needed to further refine this model and increase its performance on unseen data. As a next step `MyHomeSearch` will continue refining its predictive model with the goal of explaining 95%-99% of the variation in the sale price. At this moment, if new data becomes available, this model can be trained and tested on the new data to continue refining it.
