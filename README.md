# TFS
Risk Analysis Code Breakdown

The following code attempts to import, clean, analyze and visualize card expenditure data from 2010 to 2019. The project aims to propose qualitative and quantifiable risk metrics to ascertain the potential risk for each of the numerous card transactions. 

I begin by importing the data and only including columns that would be necessary for our analysis. I have decided to change all values in amount as absolute values so any form of refunds are treated as normal transactions. The higher the value for money leaving/entering the account, the riskier the transaction.

Then I proceeded to group the client IDs by their total amount transacted. All client IDs below the 30th percentile are treated as low-value clients, clients between the 30th and 70th are treated as medium and those above the 70th percentile are treated as high-value clients. 30 and 70 felt like suitable enough divisions compared to a constant value of $5000 transacted for example. 


