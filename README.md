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
To understand the structure of the country table: columns, their data types, and constraints. I used this query ```%sql describe country```.

This query removes duplicate rows from the country table by ensuring that only unique entries, based on the Code column, are retained. 
```%%sql
delete from country
where Code not in 
(select * from 
    (select Code from country group by Code) subquery);```

## Relevance
This datasets offers valuable insights into worldwide demographics, economics and languages which is useful in decision-making, effective planning and purposeful interventions across differnts fields in the society. 

## Specific Case Study
- Provides geographical information for mapping and analysis
- Helps with in-depth socio-economic studies and visualizations.
- App developers requiring geographic and demographic information rely on these information.




