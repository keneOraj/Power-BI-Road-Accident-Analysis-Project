# Road Accident Analysis Dashboard

### Dashboard Link : https://app.powerbi.com/view?r=eyJrIjoiMDI2MTAyMTUtNWI2Ni00NmY4LTlkYTgtMmMzMzQ3Y2FkZGJlIiwidCI6IjUxZWM2MGUzLWUzOWEtNDk5ZC1iM2U4LTRkZTQyNDNlYTExYSJ9&pageName=ReportSection

## Problem Statement

In response to the critical need for enhanced road safety and the reduction of traffic accidents, I decided to develop a comprehensive Road Accident Analysis Power BI Dashboard. This initiative is driven by the increasing importance of data-driven decision-making to address road safety challenges and promote evidence-based interventions. The Road Accident Analysis Power BI Dashboard will leverage advanced analytics and visualizations to provide key stakeholders, including traffic authorities, policymakers, and law enforcement agencies, with actionable insights into road accident trends, contributing factors, and potential countermeasures.


### Steps followed 

- Step 1 : Loaded data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed errors & empty values were not present in any of the columns.
- Step 5 : Created a date table for time intelligence functions. Creating a date table is essential when you want to calculate measures such as TOTALYTD, MTD. 
- Step 6 : Data Modelling : created a one to many relationship between the date and the data table.
- Step 7 : Imported background design which was created in powerpoint 
- Step 8 : Calculating measures 
- Step 9 : Data visualization and charts design.
- Step 9 : Insights 
           

## Requirements 

Primary KPI - Total casualties, total accident, total casualties by accident severity for current year and YOY growth.

Secondary KPI's - Total casualties with respect to vehicle type for current year.

Monthly trend showing comparison of casualties for current year and previous year.

Casualties by road type for current year.

Current year casualties by area/location and by day/night

Total casualties and total accidents by location


## Project Stakeholders

Ministry of transport

Road transport Department

Police Force 

Emergency Services Department

Road Safety corps 

Transport Operators 

Traffic Management Agencies

The Public

The Media


## DAX Measures Calculated

CY Accidents = TOTALYTD(COUNT(Data[Accident_Index]), 'Date'[Date])

CY Casualties = TOTALYTD(SUM(Data[Number_of_Casualties]), 'Date'[Date])

PY Accidents = CALCULATE(COUNT(Data[Accident_Index]), SAMEPERIODLASTYEAR('Date'[Date]))

PY Casualties = CALCULATE(SUM(Data[Number_of_Casualties]), SAMEPERIODLASTYEAR('Date'[Date]))

YOY Accidents = ([CY Accidents]-[PY Accidents])/[PY Accidents]

YOY Casualties = ([CY Casualties]-[PY Casualties])/[PY Casualties]
