# Project Title: What Key Factors Significantly Impact Suicide Rates in the United States?

![Alt text](miscellaneous/sadness-5520345_1920.jpg) 

## Project Description
Suicides is one of the leading causes of death in the United States. According to the U.S. Centers for Disease Control and Prevention (CDC), in 2022 alone, there are over 49,000 people who died by suicide, and 1 person dies every 11 minutes due to suicide.

Because suicide has long been a pressing issue, this project focuses on an Exploratory Data Analysis of the different factors influencing suicide in the United States for the years 2000 to 2022. Data on U.S. demographics (gender, age group, race, and population density), socioeconomic factors (unemployment, median household income, gun ownership, and veteran deaths), and psychosocial factors (illicit drug use and depression) were collected from various credible sources. Additionally, further analysis on these factors are done with respect to its impact on Suicide Rates across the United States.

## Installation
To run the code in `code/`, install the following Python packages:
```bash
pip install numpy
pip install pandas
pip install seaborn
pip install plotly
pip install geopandas
pip install folium
pip install requests
pip install kaleido
```
## Usage
To execute the code, please make sure to reference the Python Notebook from  `code/`  and the processed datasets from  `dataset/`. 

The code will first run the imports of the needed Python packages above, then reference the files from `dataset/`, clean and transform the files from `dataset/` , merge the dataframes, and run the visualizations and charts as documented in the main notebook in `code/`.

## Project Structure
The folder structure for this project is structured into three:
1. `raw_datasets/`, which contains most of the original, unmodified datasets from various sources. These files are then manually processed via Excel and are stored in the `datasets/` folder.
2. `datasets/`, which contains the processed files via Excel, as well as some raw datasets which were only processed via Python. The datasets processed via Python are cleaned using the Main Python Notebook.ipynb in `code `.
3. `code/`, which contains the main notebook for further cleansing of the datasets, and more importantly, the Exploratory Data Analysis and Visualizations for the project.

### Raw Data (raw_datasets/)
The folder `raw_datasets/` include some of the original, unmodified datasets. These files were manually cleaned and transformed using Excel, due to the difference in structure and file type. The processed versions of these files are then stored in `datasets/`.

This folder contains the following files:
- 2000 to 2020 Year State Suicides.txt: This file contains raw data from CDC Wonder on the Suicide Deaths per Year and State for the years 2000 to 2020.
- 2018 to 2022 Year State Suicides.txt: This file contains raw data from CDC Wonder on the Suicide Deaths per Year and State for the years 2018 to 2022.
- 2000 to 2020 Year State Age Gender Suicides.txt: This file contains raw data from CDC Wonder on the Suicide Deaths per Year, State, Age Group and Gender for the years 2000 to 2020.
- 2018 to 2022 Year State Age Gender Suicides.txt: This file contains raw data from CDC Wonder on the Suicide Deaths per Year, State, Age Group and Gender for the years 2018 to 2022.
- 2000 to 2020 Year State Gender Race Suicides.txt: This file contains raw data from CDC Wonder on the Suicide Deaths per Year, State, Gender and Race for the years 2000 to 2020.
- 2018 to 2022 Year State Gender Race Suicides.txt: This file contains raw data from CDC Wonder on the Suicide Deaths per Year, State, Gender and Race for the years 2018 to 2022.
- H08 Median Household Income by State 1984 to 2023.xlsx: This file contains raw data from US Census Bureau on the Median Household Income for the years 1984 to 2023.
- NSDUHsaeTotals2014.xlsx: This file contains data from 2014 National Surveys on Drug Use and Health (NSDUH)
- NSDUHsaeTotals2015.xlsx: This file contains data from 2015 National Surveys on Drug Use and Health (NSDUH)
- NSDUHsaeTotals2016.xlsx: This file contains data from 2016 National Surveys on Drug Use and Health (NSDUH)
- NSDUHsaeTotals2017.xlsx: This file contains data from 2017 National Surveys on Drug Use and Health (NSDUH)
- NSDUHsaeTotals2018.xlsx: This file contains data from 2018 National Surveys on Drug Use and Health (NSDUH)
- 2019NSDUHsaeTotals.xlsx: This file contains data from 2019 National Surveys on Drug Use and Health (NSDUH)
- 2022-nsduh-sae-totals-tables.xlsx: This file contains data from 2022 National Surveys on Drug Use and Health (NSDUH)
- TL-354-State-Level Estimates of Household Firearm Ownership.xlsx: This file contains the Average Household Firearm Rate data per Year and State from the RAND Corporation for 1980 to 2016
- VA_State_Sheets_2001-2021_Appendix_508.xlsx: This file contains state level veteran suicide data
- Depression 2020.xlsx: This file contains state level data of depression per 100k of state population in 2020
- Depression 2021.xlsx: This file contains state level data of depression per 100k of state population in 2021
- Depression 2022.xlsx: This file contains state level data of depression per 100k of state population in 2022

### Datasets (datasets/)
The folder `datasets` contain the processed datasets after some of the raw data from `raw_datasets/` have been initially cleaned using Excel. The files in this folder are ready for import and further cleaning in the `code/` main notebook using Python. 

This folder contains the following processed files. Also detailed below is an overview of how manual processing via Excel was done:
- year_state_suicide.csv: This file contains manually processed and initially cleaned data from the CDC Wonder raw datasets, specifically 2000 to 2020 Year State Suicides.txt and 2018 to 2022 Year State Suicides.txt.
  1. The raw datasets above were merged. The overlapping rows of data from 2018 to 2020 were removed in the 2018 to 2022 Year State Suicides.txt.
  2. The 'Notes' column was removed.
- year_state_age_gender.csv: This file contains manually processed and initially cleaned data from the CDC Wonder raw datasets, specifically 2000 to 2020 Year State Age Gender Suicides.txt and 2018 to 2022 Year State Age Gender Suicides.txt.
  1. The raw datasets above were merged. The overlapping rows of data from 2018 to 2020 were removed in the 2018 to 2022 Year State Age Gender Suicides.txt.
  2. The 'Notes' column was removed.
- year_state_gender_race.csv: This file contains manually processed and initially cleaned data from the CDC Wonder raw datasets, specifically 2000 to 2020 Year State Gender Race Suicides.txt and 2018 to 2022 Year State Gender Race Suicides.txt.
  1. The raw datasets above were merged. The overlapping rows of data from 2018 to 2020 were removed in the 2018 to 2022 Year State Gender Race Suicides.txt.
  2. The 'Notes' column was removed.
- median_household_income_by_state_2000-2023.csv: This file contains manually processed and initially cleaned data from the US Census Bureau Median Income raw dataset, specifically only the relevant years from H08 Median Household Income by State 1984 to 2023.xlsx.
  1. The first 7 rows from the raw dataset were removed, which only contained text information on the data.
  2. There are 2 columns for the year 2017. The column '2017 (40)' was chosen as it reflected estimates from an updated data processing system based on the footnote 40 from https://www.census.gov/topics/income-poverty/income/guidance/cps-historic-footnotes.html.
  3. There are 2 columns for the year 2013. A new column for 2013 was created, where a weighted average of the median income for 2013 was calculated, based on footnotes 38 and 39 from the above link.
- Illicit Drug Use Other Than Mar.csv: This file contains illicit drug use data Substance Abuse and Mental Health Services Administration for years 2014, 2016 to 2019, and 2022 from the raw files of NSDUHsaeTotals2014.xlsx, NSDUHsae2015.xlsx, NSDUHsae2016.xlsx, NSDUHsae2017.xlsx, NSDUHsaeTotals2018.xlsx, 2019NSDUHsaeTotals.xlsx, and 2022-nsduh-sae-totals-tables.xlsx.
  1. Raw data from the years were merged to 1 dataset.
  2. Further processing was done via Python as documented in `code`.
- gun_ownership_data.csv: This file contains manually processed and initially cleaned data from RAND Corporation, specifically the TL-354-State-Level Estimates of Household Firearm Ownership.xlsx file.
  1. Raw data from the 'State-Level Data & Factor Score' tab was copy and pasted to a clean CSV file.
- veteran_suicides_by_states.csv: This file contains the veteran suicides per year, geographic region and state from the US Department of Veterans Affairs for years 2001 to 2021, specifically from the raw file VA_State_Sheets_2001-2021_Appendix_508.xlsx.
  1. Raw data from the 'Veteran Suicides by State' tab was copy and pasted to a clean CSV file.
- Depression all.csv: This file combined the depression per 100k from depression dataset within years 2020 to 2022, specifically the files Depression 2020.xlsx, Depression 2021.xlsx, and Depression 2022.xlsx.
  1. Raw data from the different years were merged to 1 dataset.

The  `datasets/` folder also includes two raw datasets which only underwent cleaning via Python (and not Excel). The code for cleaning these files are documented in `code/`.
- Unemployment in America Per US State.csv: This file contains unemployment data from the US Bureau of Labor Statistics from 2000 to 2022.
- us_states_areas.csv: This file contains the Total Area in square miles for each state from the US Census Bureau.

### Main Notebook Code (code/)
The folder `code/` contains 2 sub-folders:
1. `final-notebook/` which contains the main project notebook:
   - **TheChartToppers_FinalNotebook.ipynb:** This notebook contains the main original code for the Exploratory Data Analysis spanning the years 2000 to 2022. For the project, running this notebook is sufficient.
3. `supporting-notebooks/` which contains two Python supporting notebooks:
   - **2000-2010_notebook.ipynb:** This notebook contains the same Python code as the main notebook TheChartToppers_FinalNotebook.ipynb, but only filtered for the years 2000 to 2010, to compare the Exploratory Data Analysis results from the earliest 11 years of the dataset.
   - **2011-2022_notebook.ipynb:** This notebook contains the same Python code as the main notebook TheChartToppers_FinalNotebook.ipynb, but only filtered for the years 2011 to 2022, to compare the Exploratory Data Analysis results from the most recent 12 years of the dataset.

Each notebook is divided into 2 parts:
- **Importing and Cleaning the Datasets:** This section includes all of the raw and processed datasets from  `datasets/`, which are imported and further cleaned in the main notebook TheChartToppers_FinalNotebook.ipynb.
- **Exploratory Data Analysis:** This section presents the different line charts, bar charts, maps, scatter plots and other types of visualizations to answer the project’s main research question: *What key factors significantly impact suicide rates in the United States?*
The visualizations are done using different Python packages such as plotly and matplotlib, which needs to be installed before running the Main Python Notebook. See installation guide above. 

### Miscellaneous (miscellaneous/)
The folder `miscellaneous/` contains images and other files relevant to the project.

## Data Sources
Below are the formal APA citations where the files from `raw_datasets/` and `datasets/` were obtained from.

**Demographic Data:**
1. 2000 to 2020 Year State Suicides.txt: Centers for Disease Control and Prevention. (n.d.). State suicide mortality rates (2000 to 2020) [Data set]. CDC Wonder Current Final Multiple Cause of Death Data. Retrieved October 18, 2024 from https://wonder.cdc.gov/mcd.html
2. 2018 to 2022 Year State Suicides.txt: Centers for Disease Control and Prevention. (n.d.). State suicide mortality rates (2018 to 2022) [Data set]. CDC Wonder Current Final Multiple Cause of Death Data. Retrieved October 18, 2024 from https://wonder.cdc.gov/mcd.html
3. 2000 to 2020 Year State Age Gender Suicides.txt: Centers for Disease Control and Prevention. (n.d.). State Suicide Mortality Rates by Year, State, Age Group, Gender (2000 to 2020)  [Data set]. CDC Wonder Current Final Multiple Cause of Death Data. Retrieved October 21, 2024 from https://wonder.cdc.gov/mcd.html
4. 2018 to 2022 Year State Age Gender Suicides.txt: Centers for Disease Control and Prevention. (n.d.). State Suicide Mortality Rates by Year, State, Age Group, Gender (2018 to 2022)  [Data set]. CDC Wonder Current Final Multiple Cause of Death Data. Retrieved October 21, 2024 from https://wonder.cdc.gov/mcd.html
5. 2000 to 2020 Year State Gender Race.txt: Centers for Disease Control and Prevention. (n.d.). State Suicide Mortality Rates by Year, State, Gender, Race (2000 to 2020)  [Data set]. CDC Wonder Current Final Multiple Cause of Death Data. Retrieved October 25, 2024 from https://wonder.cdc.gov/mcd.html
6. 2018 to 2022 Year State Gender Race.txt: Centers for Disease Control and Prevention. (n.d.). State Suicide Mortality Rates by Year, State, Gender, Race (2018 to 2022)  [Data set]. CDC Wonder Current Final Multiple Cause of Death Data. Retrieved October 25, 2024 from https://wonder.cdc.gov/mcd.html
7. VA_State_Sheets_2001-2021_Appendix_508.xlsx: U.S. Department of Veterans Affairs. (n.d.). Veteran suicide data and reporting. VA Mental Health. Retrieved October 19, 2024 from https://www.mentalhealth.va.gov/suicide_prevention/data.asp
8. us_states_areas.csv: U.S. Census Bureau. (2010). Geographic area measurement - state land areas [Data file: us_states_areas.csv]. Retrieved October 25, 2024, from https://www.census.gov/geographies/reference-files/2010/geo/state-area.html

**Socioeconomic Data:**
1. Unemployment in America Per US State.csv: The Bureau of Labor Statistics. (2024). Unemployment in America, per US state [Data set]. US Bureau of Labor Statistics. Retrieved September 30, 2024 from https://www.bls.gov/web/laus.supp.toc.htm
2. H08 Median Household Income by State 1984 to 2023.xlsx: United States Census Bureau. (2024). Table H-8. Median household income by state [Data set]. US Census Bureau Historical Income Tables: Households. Retrieved October 6, 2024 from https://www.census.gov/data/tables/time-series/demo/income-poverty/historical-income-households.html 
3. TL-354-State-Level Estimates of Household Firearm Ownership.xlsx: Schell, T. L., Peterson, S., Vegetabile, B. G., Scherling, A., Smart, R., & Morral, A. R. (2020). State-level estimates of household firearm ownership [Data set]. RAND Corporation. Retrieved October 20, 2024 from https://www.rand.org/pubs/tools/TL354.html 

**Psychosocial Data:**
1. NSDUHsaeTotals2014.xlsx: Substance Abuse and Mental Health Services Administration. (n.d.). Illicit drug use in America: National Survey on Drug Use and Health for 2014 (NSDUH) state data [Data set]. SAMHSA. Retrieved October 13, 2024, from https://www.samhsa.gov/data/nsduh/state-reports 
2. NSDUHsaeTotals2015.xlsx: Substance Abuse and Mental Health Services Administration. (n.d.). Illicit drug use in America: National Survey on Drug Use and Health for 2015 (NSDUH) state data [Data set]. SAMHSA. Retrieved October 13, 2024, from https://www.samhsa.gov/data/nsduh/state-reports
3. NSDUHsaeTotals2016.xlsx: Substance Abuse and Mental Health Services Administration. (n.d.). Illicit drug use in America: National Survey on Drug Use and Health for 2016 (NSDUH) state data [Data set]. SAMHSA. Retrieved October 13, 2024, from https://www.samhsa.gov/data/nsduh/state-reports
4. NSDUHsaeTotals2017.xlsx: Substance Abuse and Mental Health Services Administration. (n.d.). Illicit drug use in America: National Survey on Drug Use and Health for 2017 (NSDUH) state data [Data set]. SAMHSA. Retrieved October 13, 2024, from https://www.samhsa.gov/data/nsduh/state-reports 
5. NSDUHsaeTotals2018.xlsx: Substance Abuse and Mental Health Services Administration. (n.d.). Illicit drug use in America: National Survey on Drug Use and Health for 2018 (NSDUH) state data [Data set]. SAMHSA. Retrieved October 13, 2024, from https://www.samhsa.gov/data/nsduh/state-reports 
6. 2019NSDUHsaeTotals.xlsx: Substance Abuse and Mental Health Services Administration. (n.d.). Illicit drug use in America: National Survey on Drug Use and Health for 2019 (NSDUH) state data [Data set]. SAMHSA. Retrieved October 13, 2024, from https://www.samhsa.gov/data/nsduh/state-reports 
7. 2022-nsduh-sae-totals-tables.xlsx: Substance Abuse and Mental Health Services Administration. (n.d.). Illicit drug use in America: National Survey on Drug Use and Health for 2022 (NSDUH) state data [Data set]. SAMHSA. Retrieved October 13, 2024, from https://www.samhsa.gov/data/nsduh/state-reports 
8. Depression 2020.xlsx: Mental Health America. (2020-2024). County and State Data Map: Defining Mental Health Across Communities for 2020 [Data set]. MHA State and County Data Map. Retrieved October 26, 2024 from https://mhanational.org/mhamapping/mha-state-county-data 
9. Depression 2021.xlsx: Mental Health America. (2020-2024). County and State Data Map: Defining Mental Health Across Communities for 2021 [Data set]. MHA State and County Data Map. Retrieved October 26, 2024 from https://mhanational.org/mhamapping/mha-state-county-data 
10. Depression 2022.xlsx: Mental Health America. (2020-2024). County and State Data Map: Defining Mental Health Across Communities for 2022 [Data set]. MHA State and County Data Map. Retrieved October 26, 2024 from https://mhanational.org/mhamapping/mha-state-county-data 

