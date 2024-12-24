# World
This project is to showcase my SQL skills.

----

## Introduction
This dataset was obtained from mySQL workbench and I found it useful to analyse the data from different geographical location, demography and socio-economic. It typically has 3 main tables. 

Listed below are the datasets used in this project:

[CITY](https://github.com/Farouk-Muda/World/blob/main/city.csv) : The city dataset contains thousands of rows and includes the following columns:
- ID: A unique identifier for each city.
- Name: The name of the city.
- CountryCode: The code representing the country of the city.
- District: The district or region where the city is located.
- Population: The population count of the city.


[COUNTRY](https://github.com/Farouk-Muda/World/blob/main/country.csv) : The country dataset contains 239 rows and provides detailed information about countries with the following columns:
- Code: A unique country code.
- Name: The country's name.
- Continent: The continent where the country is located.
- Region: The specific region within the continent.
- SurfaceArea: The total surface area of the country.
- IndepYear: The year of independence.
- Population: The total population of the country.
- LifeExpectancy: The average life expectancy.
- GNP: The Gross National Product (current).
- GNPOld: The previous year's Gross National Product.
- LocalName: The country's local name.
- GovernmentForm: The form of government.
- HeadOfState: The name of the head of state.
- Capital: The capital city's identifier.
- Code2: An alternate two-character country code

  
[COUNTRYLANGUAGE](https://github.com/Farouk-Muda/World/blob/main/countrylanguage.csv): The countryLanguage dataset contains 984 rows and provides insights into the languages spoken in various countries with the following columns:
- CountryCode: The code representing the country.
- Language: The name of the language.
- IsOfficial: Indicates whether the language is officially recognized.
- Percentage: The percentage of the population speaking the language.

To analyze the data efficiently in Python, I integrated SQL functionality into Jupyter Notebook using the *ipython-sql* and *sqlalchemy libraries*.

## SQL skills applied

- Window Functions
- CTEs
- Aggregations
- JOINs

## Data Exploration
To understand the structure of the country table: columns, their data types, and constraints. I used this query ```%sql describe country.```
Added a PopulationDensity column to the country table: This step is necessary to store the population density for each country, which can be useful for demographic and geographic analysis. ```%%sql
alter table country
add column PopulationDensity float; ```

Updated the PopulationDensity column by calculating population divided by surface area for all rows: This calculation ensures that each country's population density is correctly derived from its population and surface area, enabling accurate analysis. ```%%sql
update country
set PopulationDensity = Population / SurfaceArea; ```

Modified the IndepYear column in the country table to be of type INT: Changing the column type to INT ensures that the year of independence is stored as a numeric value, making it easier to perform year-based calculations and comparisons. ```%%sql
alter table country
modify column IndepYear INT; ```

I explored 7 critical questions in my analysis below:
- 1. What is the total population by continent
- 2. Calculating the population density (Population / SurfaceArea) to determine how populated different regions are.
- 3. Calculate Gross National Product (GNP) per capita (GNP / Population) to compare the economic well-being of citizens in different countries.
- 4. Comparing LifeExpectancy and GNP to determine how countries wealth impact their health
- 5. Exploring the distribution of differnt government form
- 6. Analysing all Independence Year to find out years countries gain independence.
- 7. Exploring the list of cities along with their corresponding countries and the languages 
spoken in those countries:

## Relevance / Insights
- The total populations by continent show **Asia** as the most populous, with North America, Europe, and Africa following, while Oceania and Antarctica have significantly smaller populations.
- The data reveals that **densely populated areas like Macao, Monaco, and Hong Kong** have significantly higher population densities, while regions like **Antarctica, Greenland, and several small islands have negligible or no populations**.
- Countries with **high GNP per capita, such as Luxembourg, Switzerland, and Bermuda**, contrast sharply with **lower-income nations like Somalia, Ethiopia, and Congo**, while numerous small islands and territories report negligible or no economic output.
- It reveals significant variation in life expectancy and GNP across countries, with **wealthier nations generally having higher life expectancies**, while many developing nations show lower life expectancy and GNP values.
- The data shows that **the majority of countries are republics**, with a smaller number following forms such as constitutional monarchies, federal republics, and various territories or special administrative regions.
- The data shows that **1991 and 1960 marked significant years for independence**, with 18 countries gaining independence in each, while other years, like 1975 and 1962, also saw notable independence movements.


## Recommendations
- 1. Asia's dominant population suggests a focus on regional policies addressing overpopulation and infrastructure needs, particularly in densely populated countries.
- 2. Densely populated areas should prioritize sustainable urban planning, while regions with negligible populations may focus on conservation and environmental protection.
- 3. High GNP per capita countries should continue investing in innovation and global partnerships, while lower-income nations may benefit from international aid and economic development programs.
- 4. Wealthier nations' higher life expectancy underscores the importance of healthcare access and quality of life improvements in developing nations to narrow these disparities.
- 5. The prevalence of republics highlights the need for democratization efforts and governance improvements in nations with other forms of government.
- 6. 1991 and 1960's significance in independence underscores the importance of supporting newly independent countries in building stable economies and governance structures.




