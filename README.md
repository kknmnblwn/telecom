# Problem Statement
Which geographic clusters in Davao City suffer from the highest network degradation during peak hours (6 PM – 11 PM), and which sub-districts should be prioritized for Fiber-to-the-Home (FTTH) infrastructure upgrades based on projected ROI?

# Data
The data was derived through the Prompt Engineering. Here's my prompt using Google Gemini.

<i>I am an aspiring Data Analyst and I want to make a portfolio with a Problem Statement below but I need a raw data (at least 3years) that needs to be cleaned up and manipulated. Generate one and make it into a downloadable .csv file.

"Which geographic clusters in Davao City suffer from the highest network degradation during peak hours (6 PM – 11 PM), and which sub-districts should be prioritized for Fiber-to-the-Home (FTTH) infrastructure upgrades based on projected ROI?”</i>

# Methodology
## Python
With the use of Google Colab, I loaded the .csv file and initially inspected the whole sheet using the .info() where I found missing values from the columns. Assumed that since there were no values in the cell, I went ahead and filled it out with "0". I also changed the data types on some columns and transformed the 'district' and 'sub_district' columns into its proper form. After that, I exported a transformed data into an .xlsx file.
## Excel
Used Excel to clean data in the dataset that was not easily visible through Google Colab (Python).

I've filtered out all the negative percentages in the <i>packet_loss_pct</i> column and changed it to 0. Having a -99.00% packet loss is impossible and may be due to a sensor glitch. 
## Power BI


# Insights
# Recommendations
