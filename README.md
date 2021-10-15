# COVID-19 Timeline Analysis
#### Author : Siddhartha Roy Chowdhury

COVID-19 Timeline Analysis is a data analytics project to analyze and visualize the impact of the COVID-19 pandemic over time around the world. Tools used include MS-Excel, SQL Server & Tableau Desktop.

## Data Preparation
COVID-19 Timeline Analysis is made using the "Data on COVID-19 (coronavirus) by Our World in Data" dataset. It is maintained by [_Our World in Data_](https://ourworldindata.org/coronavirus). The dataset is downloaded, checked and uploaded to SQL Server under the name "CovidCases.csv" for data cleaning and analysis.

Link to original dataset repository: https://github.com/owid/covid-19-data/tree/master/public/data/ 

## Data Cleaning and Analysis using SQL
During data exploration, a log of the things found and actions taken was maintained. It is given below :
- Column types are all 'varchar'. Some needed to be changed to numeric type such as 'float' for proper calculation. It is done using the Alter Column command.
- Dirty data in continent and location column is fixed by not selecting continent fields with blank data. Any data related to that blank field is irrelevant/wasted as it leads no proper conclusion. 
- ICU/Hospitalized Patient data is not sufficient enough to produce any accurate, unbiased conclusion. The data from majority of the countries is absent, so no global graph can be drawn from such data.
- Insufficient Reproduction rate data. The Reproduction rate data seems to be absent in many fields and doesn't seem to have a direct correlation with total confirmed cases.
- Extreme Poverty data is maybe unclean. It doesn't seem to affect the death rate of a country.
- No link can be established between columns. Example - if a smoker is also over 60, is vaccinated or not, did suffer from covid or not. Without such data, an accurate conclusion cannot be drawn since we cannot confirm if one causes the other.
- Final Dataset is selected based on the purpose of this project, which is timeline analysis, so that we do not divert from the original purpose. The new dataset named "Covid19Tab.csv" is exported from SQL Server and is ready to be used as a data source of Tableau visualization. The final dataset is also uploaded to github under the same name.
### Final Dataset Metadata
| Variable                         | Description                                                           |
|:---------------------------------|:----------------------------------------------------------------------|
| `total_cases`                    | Total confirmed cases of COVID-19                                     |
| `new_cases`                      | New confirmed cases of COVID-19                                       |
| `total_deaths`                   | Total deaths attributed to COVID-19                                   |
| `new_deaths`                     | New deaths attributed to COVID-19                                     |
| `positive_rate`                  | The share of COVID-19 tests that are positive, given as a rolling 7-day average|
| `total_tests`                    | Total tests for COVID-19                                              |
| `new_tests`                      | New tests for COVID-19 (only calculated for consecutive days)         |
| `total_vaccinations`             | Total number of COVID-19 vaccination doses administered               |
| `people_vaccinated`              | Total number of people who received at least one vaccine dose         |
| `people_fully_vaccinated`        | Total number of people who received all doses prescribed by the vaccination protocol | 
| `continent`                      | Continent of the geographical location                                |
| `location`                       | Geographical location                                                 |
| `date`                           | Date of observation                                                   |
| `population`                     | Population in 2020                                                    |

## Data Visualiztion using Tableau
A timeline dashboard is created using Tableau Desktop and is published on Tableau Public.

[Link to the dashboard](https://public.tableau.com/views/Covid-19TimelineAnalysis_16342092518220/Dashboard1?:language=en-GB&publish=yes&:display_count=n&:origin=viz_share_link)

The dashboard includes:
- Covid19 Cases World Map
- Total Cases Confirmed Graph
- Top 15 Countries with the Most Cases Graph
- New Cases vs New Death Graph
- Total Vaccination vs Population Graph
- People Partially Vaccinated vs People Fully Vaccinated
- Total Tests vs Positivity Rate

Hence, the Timeline Analysis is complete and is available in Tableau Public.
