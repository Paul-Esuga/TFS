Risk Analysis Code Breakdown

The following code attempts to import, clean, analyze and visualize card expenditure data from 2010 to 2019. The aim of the project is to propose qualitative and quantifiable risk metrics to ascertain the potential risk for each of the numerous card transactions. 

I begin by importing the data and only including columns that would be necessary for our analysis. I have decided to change all values in amount as absolute values so any form of refunds are treated as normal transactions. The higher the value for money leaving/entering the account, the riskier the transaction

Then I proceeded to group the client IDs by their total amount transacted. All client ids below the 30th percentile are treated as low value clients, clients between the 30th and 70th are treated as medium and those above the 70th percentile are treated as high value clients. 30 and 70 felt like suitable enough divisions compared to a constant value of $5000 transacted for example.

Next I created a variable that measures the value of a clients risk based on their customer history. The more a client transacts, the smaller the value of this client risk decreases to show appreciation for consistency. I used a logarithmic decay function to represent this. Similar to my normalization function for amount. Because there was such a large disparity between the amount values, I used a log function to make the values more linear/easier to work with. 

For each type of transaction: chip, swipe and online, I assigned a suitable risk factor. 1 for swipe as it is the easiest to commit fraud and it requires the least authentication. Online requires otp so it is more secure, hence the 0.5 rating. Chip, requiring pin, is the most secure and deserves the 0.2 risk rating. No 0s as I still believe there could still be some risk if someone gets hands on your pin.  I also assigned a risk rating for if the transaction ran into an error or not. 

I separated the date column into date and time so I could make transactions done in the very late hours of the night to be riskier. Day time transactions are safe, late night are riskier and very early morning the riskiest of them all. 

Then I weighted all my risk metrics and developed a more wholistic total risk value for the dataset. Finally I plotted 3 different scatter plots with varying levels of details about the data set

