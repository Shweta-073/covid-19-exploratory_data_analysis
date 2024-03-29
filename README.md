An exploratory data analysis project on Covid19 cases, deaths, and vaccinations from, 1st Jan, 2020 to 12th May, 2021. This project is purely based on SQL, employing its innate capabilities: User-defined Procedures, Temp Tables, CTE, and Views.

Table of Contents

Dataset Overview
Importing Dataset Into SQL Server
Analysis
Dataset Overview
Data Source: ourworldindata.org Links: https://covid.ourworldindata.org/data/owid-covid-data.xlsx https://github.com/owid/covid-19-data/tree/master/public/data

Rows: 87743 Columns: 59

Many null values were found in the dataset. This has been taken into consideration during the analysis

Continent column contains names of continents. Location column contains names of continents and countries. While analyzing country wise data, it is important to exclude rows with location set to continent name. Example:

SELECT location, MAX(total_cases)
FROM covid19timeseries
WHERE continent IS NOT NULL
continent	location
Asia
Africa
South America
North America
Europe
Oceania
Datatypes need to be corrected to a Float type as many columns would be imported as varchar
Importing Dataset Into SQL Server
It is recommended that SQL Server Import and Export Data (64 bit) wizard is launched from the Start Menu, and not the inbuilt option available within SSMS

Analysis

1) List Of Countries Affected By Covid19
2) Number Of Countries Affected By Covid19
3) Date Of First Case Reported For Each Country
4) Total Cases Vs Total Deaths (All Countries) - Observing Change With Time
5) Total Case Vs Total Deaths (India) - Observing Change With Time
6) CASES_SUMMARY: Isolating Total Cases, Total Deaths For Each Country
7) Cases And Deaths Compared To Population
8) Cases And Deaths Compared To Population (India)
9) Highest To Lowest Death Count
10) Cases And Deaths - Continent Wise
11) Vaccination Start Date For Countries
12) Total No. Of People Vaccinated, Vaccination Percentage Of Population
13) TOP 5 countries with most people vaccinated (United States, India, United Kingdom)
14) Comparing Diabetes Prevalence, Cardiovascular Death Rate To Death Percentage
15) Comparing Stringency Index to Infected Population And Death Percentage
16) Comparing Smokers to Infected Population And Death Percentage
17) Comparing Percentage Of Population Over 65 And 70 To Infected Population And Death Percentage
18) Comparing GDP, Human Development Index, Extreme Poverty To Vaccinated Population Percentage
19) Correlation Between New Vaccinations And New Cases For Top 5 Countries with Highest Count Of Vaccination
20) Correlation Between New Vaccinations And New Deaths For Top 5 Countries with Highest Count Of Vaccination
21) Correlation Between New Vaccinations And Stringency Index For Top 5 Countries with Highest Count Of Vaccination
