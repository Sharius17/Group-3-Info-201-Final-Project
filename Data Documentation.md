# Data Documentation 
## Original data sources
The table S0802 from the American Community Survey (ACS) is from the U.S. Census and accessed through tidycensus. https://data.census.gov/table/ACSST1Y2021.S0802?q=commute 

Car crash data is from the Washington State Department of Transportation. https://remoteapps.wsdot.wa.gov/highwaysafety/collision/data/portal/public/

Gasoline price data is from the U.S. Energy Information Administration.  
Seattle data: https://www.eia.gov/dnav/pet/hist/LeafHandler.ashx?n=pet&s=emm_epmru_pte_y48se_dpg&f=a  
Washington data: https://www.eia.gov/dnav/pet/hist/LeafHandler.ashx?n=PET&s=EMM_EPM0U_PTE_SWA_DPG&f=M 

## Explanation of variables
location: where the data pertains to (either Seattle city or Washington state)
variable: the code of the given question in the ACS. The format is table_column_row (e.g.: S0802_C01_001)\
estimate: the estimated value for the given question in the ACS\
moe: the margin of error for the given question in the ACS\
year: which year the data pertains to\
trait1 - trait6: labels that explain what a particular ACS code measures. These are pulled from tidycensus' codebook, which separates traits of the label through delimiters. For example, `S0802_C01_039` actually means `Estimate!!Total!!POVERTY STATUS IN THE PAST 12 MONTHS!!Workers 16 years and over for whom poverty status is determined!!Below 100 percent of the poverty level.` We separated this one string out into 6 variables. Not all rows fill all 6 variables, how many levels they need to be described varies on a case-by-case basis.\
total_crashes: all crashes recorded by police officers for each year, separated by location.\
gas_price: average gasoline price for each year, separated by location.\

## Basic summary statistics
Number of rows: 9696
Number of columns: 13
Missing/invalid values: We do not have data for the year 2020 because ACS survey data was not provided due to the effects of the COVID-19 pandemic. Additionally, trait1 - trait6 have some NA values for ACS questions which did not require 6 levels to be described.


