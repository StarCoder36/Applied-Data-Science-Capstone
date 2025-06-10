# IBM Applied Data Science Capstone
IBM Data Science Capstone: SpaceX Launch Success Analysis

## Introduction
Welcome to my Data Science Capstone project, where I delve into the exciting world of rocket launches, focusing on SpaceX and their groundbreaking efforts to revolutionize space travel. Let's explore the journey of SpaceX, their cost-saving strategies, and the prediction of first-stage rocket landing success.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0701EN-SkillsNetwork/api/Images/landing_1.gif)

## Background
SpaceX, a pioneering force in the space industry, is dedicated to democratizing space travel by making it affordable for everyone. The company has achieved remarkable feats, including deploying spacecraft to the International Space Station, launching a satellite constellation for global internet coverage, and conducting crewed space missions. A crucial factor contributing to SpaceX's cost-effectiveness is its innovative approach to reusing the first stage of its Falcon 9 rocket, which significantly reduces the launch cost to $62 million per launch. In contrast, other providers, unable to replicate this reusability, charge upwards of $165 million for each launch. The key to determining the launch cost lies in predicting the success of the first-stage landing. To achieve this, we harness publicly available data and employ machine learning models to forecast whether SpaceX or a competitor can successfully recover the first stage.

## Exploration

This analysis delves into several critical aspects:

+ Investigating how factors such as payload mass, launch site, number of flights, and orbits influence the success of first-stage landings.
+ Charting the progression of successful landings over time.
+ Identifying the optimal predictive model for successful landings through binary classification.

## Executive Summary
This research aims to unveil the key determinants of a successful rocket landing. The investigative journey involved the following steps:

+ **Data Collection:** Gathering data through the SpaceX REST API and web scraping techniques
+ **Data Wrangling:** Preparing the data, including creating a success/failure outcome variable.
+ **Data Exploration:** Visualizing the data to understand the impact of payload, launch site, flight number, and annual trends.
+ **Data Analysis:** Utilizing SQL to calculate statistics such as total payload, payload range for successful launches, and the total count of successful and failed outcomes.
+ **Site-Specific Success Rates:** Investigating launch site success rates and their proximity to geographical markers.
+ **Visualizing Success:** Creating visual representations of launch sites with the highest success rates and the payload ranges linked to success.
+ **Building Predictive Models:** Developing predictive models using logistic regression, support vector machine (SVM), decision tree, and K-nearest neighbor (KNN).

## Results
### Exploratory Data Analysis:

+ Notable improvement in launch success rates over time.
+ KSC LC-39A boasts the highest success rate among all landing sites.
+ Orbits ES-L1, GEO, HEO, and SSO have achieved a remarkable 100% success rate.

### Visualization / Analytics:

+ Most launch sites are strategically located near the equator, capitalizing on the Earth's rotational speed to reduce the need for additional fuel and boosters.
+ All launch sites are situated in proximity to coastlines, facilitating logistical operations.

### Predictive Analytics

+ All models exhibited similar performance on the test set, with the decision tree model slightly outperforming others when considering the .best_score_ metric.

### Methodology
## Data Collection - API

+ **Requesting Data:** Fetching data from the SpaceX API, specifically rocket launch data.
+ **Data Decoding:** Deciphering the API response using .json() and converting it into a dataframe using .json_normalize().
+ **Custom Data Functions:** Developing custom functions to extract launch information from the SpaceX API.
+ **Data Dictionary:** Creating a dictionary from the gathered data.
+ **DataFrame Creation:** Converting the dictionary into a dataframe.
+ **Data Filtering:** Filtering the dataframe to include only Falcon 9 launches.
+ **Handling Missing Data:** Replacing missing payload mass values with the calculated mean.
+ **Data Export:** Exporting the processed data to a CSV file.

## Data Collection - Web Scraping

+ **Requesting Data:** Acquiring Falcon 9 launch data from Wikipedia.
+ **BeautifulSoup Object:** Creating a BeautifulSoup object from the HTML response.
+ **Column Names Extraction:** Extracting column names from the HTML table header.
+ **Data Extraction:** Collecting data by parsing HTML tables.
+ **Data Dictionary:** Constructing a dictionary from the extracted data.
+ **DataFrame Creation:** Transforming the dictionary into a dataframe.
+ **Data Export:** Saving the processed data to a CSV file.

## Data Wrangling

+ **Outcome Transformation:** Converting landing outcomes into 1 for successful landings and 0 for unsuccessful ones.

## EDA with Visualization

+ **Visual Insights:** Generating informative charts to analyze relationships and make meaningful comparisons.

## EDA with SQL

+ **Database Querying:** Leveraging SQL to explore the data further and uncover valuable insights.

## Maps with Folium

+ **Interactive Maps:** Creating interactive maps to visualize launch sites, track launch outcomes, and assess proximity to geographical features.

## Dashboard with Plotly Dash

+ **Dynamic Dashboard:** Building a dynamic dashboard featuring pie charts illustrating successful launches and scatter charts depicting Payload Mass vs. Success Rate by Booster Version.

## Predictive Analytics

+ **Data Preparation:** Creating a NumPy array from the Class column and standardizing the data with StandardScaler.
+ **Data Splitting:** Splitting the data using train_test_split for model evaluation.
+ **Hyperparameter Optimization:** Employing GridSearchCV with cv=10 for parameter tuning across different algorithms, including logistic regression, support vector machine (SVC), decision tree (DecisionTreeClassifier), and K-Nearest Neighbor (KNeighborsClassifier).
+ **Performance Assessment:** Calculating accuracy scores on the test data using .score() for all models and evaluating the confusion matrix.
+ **Best Model Identification:** Identifying the best model using Jaccard Score, F1 Score, and Accuracy metrics.

## Conclusion

+ **Model Performance:** The predictive models demonstrated similar performance on the test set, with the decision tree model exhibiting a slight advantage.
+ **Equatorial Advantage:** Most launch sites strategically position near the equator, capitalizing on Earth's rotational speed to reduce launch costs.
+ **Coastal Convenience:** All launch sites are strategically located near coastlines, simplifying logistical operations.
+ **Launch Success Trend:** The data reveals a positive trend in launch success rates over time.
KSC LC-39A: This launch site stands out with the highest success rate, achieving a 100% success rate for launches weighing less than 5,500 kg.
Orbital Excellence: Orbits ES-L1, GEO, HEO, and SSO have consistently achieved a 100% success rate.
+ **Payload Mass Impact:** Across all launch sites, there is a clear correlation between higher payload mass (kg) and higher success rates.
