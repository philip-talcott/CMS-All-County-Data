

"""

This script preps the data that feeds the dashboard shown below: 

https://public.tableau.com/app/profile/phil.talcott/viz/UnderstandingMedicareinAmerica/UnitedStatesOverview

Download and unzip the data from https://www.cms.gov/files/zip/statecounty-table-all-beneficiaries.zip and place it in your working 
directory to run the script below:
    
"""

import pandas as pd 

year = '2019'

a = pd.read_excel('State County All Table 2019.xlsx', sheet_name = 'State_county '+year, skiprows = 1)

b = pd.DataFrame(a.columns.unique())

id = b[0:3]
id = id.rename(columns={0:'columns'})

b = b[3:]
b = b.rename(columns={0:'columns'})


y = []
for index, row in b.iterrows():
    y.append(row['columns'])

z = []
for index, row in id.iterrows():
    z.append(row['columns'])

df_melt = a.melt(id_vars = z, value_vars = y)

df_melt.to_excel('CMS_FFS_'+year+'.xlsx')
