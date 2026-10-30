# Davao City Internet Service: Peak-Hour Analysis
<img width="2494" height="1362" alt="59580AAC-DDC8-43EF-9BBA-E19CC2DEB688" src="https://github.com/user-attachments/assets/778b3679-51ef-41a9-85f4-b9b042bffb98" />

# Project Summary
This project studies the peak-hour internet service (IS) performance in the most populated districts in Davao City. This aims to aide our local internet service providers (ISPs) to repurpose, if needed, their upgrade budget allocation.

# Problem Statement
Identify high-stress geographic service areas in Davao City experiencing network reliability issues during peak hours (6:00 PM – 11:00 PM) to minimize customer churn and optimize capital allocation for infrastructure upgrades.

# Data
The data was derived through the Prompt Engineering. Here's my prompt using Google Gemini.

<i>I am an aspiring Data Analyst and I want to make a portfolio with a Problem Statement below but I need a raw data (at least 3years) that needs to be cleaned up and manipulated. Generate one and make it into a downloadable .csv file.

"Which geographic clusters in Davao City suffer from the highest network degradation during peak hours (6 PM – 11 PM), and which sub-districts should be prioritized for Fiber-to-the-Home (FTTH) infrastructure upgrades?”</i>

# Methodology
## Python
With the use of Google Colab, I loaded the .csv file and initially inspected the whole sheet using the .info() where I found missing values from the columns. Since I found some blank cells, I assumed they have no data for it so I filled it out with "0". I also changed the data types on some columns and transformed the 'district' and 'sub_district' columns into its proper form. After that, I exported a transformed data into an .xlsx file.

## Excel
Used Excel to clean data in the dataset that was not easily visible through Google Colab (Python). I've also utilized Excel's Pivot Table just to prepare the data that I wanted to be visualized through Power BI.

## Power BI
I used this tool for the data storytelling and in making the final dashboard.

# Key Insights
<br><img width="1200" height="655" alt="F2C5EF07-7D00-4B78-B3F0-F9A93651E4B1_1_105_c" src="https://github.com/user-attachments/assets/eb5afb2e-ec06-4abb-af8d-f08b384a1a82" />
In a span of three (3) years, a trend of increasing number in complaint tickets were noted across the seven (7) districts in Davao City.</br>

<br><img width="1254" height="626" alt="C7AB7F32-D393-4F04-9AD3-8C25FAB07E3D_1_105_c" src="https://github.com/user-attachments/assets/8b69af3b-8230-4351-b303-1ce81ad8debb" />
When compared with the total Outage Duration (in milliseconds) per District, <b>Talomo and Buhangin Districts were consistently two of the highest. Ranking 3rd in the highest Outage Duration, yet, lower compared to the other districts in Complaint Tickets Logged is the Poblacion District.</b> Although <b>Agdao District is ranked 5th in Outage Duration, its Complaint Ticket Logged was the 3rd highest.</b></br>

<br><img width="1694" height="792" alt="B673879F-EED6-4958-8155-B9EDAD5E922B" src="https://github.com/user-attachments/assets/9850a9df-bdd0-425a-8bed-d894fea337a5" />
One of the contributors for these complaint tickets is the <b>Bandwidth Utilization (%)</b>. Having at least 85% BW Util means that the highway where cars (data) pass by from point A to B is 85% full!</br>

<br><img width="1296" height="606" alt="EF78FBA5-F65F-45FE-A065-AA3EE24ED148_1_105_c" src="https://github.com/user-attachments/assets/083bf4ee-dd6a-4c43-a158-63e62a9fbd82" />
Continuing with the highway analogy, latency (measured in milliseconds) is the travel time of a single car to travel from your device to the destination server and back. <b>In this case, the districts Talomo, Buhangin and Poblacion experience the longest average latency.</b>
</br>

# Recommendations
