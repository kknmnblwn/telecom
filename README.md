# Davao City Internet Service: Peak-Hour Analysis
<img width="2502" height="1352" alt="F10F46A6-13C6-47CD-AAE0-27391D645220" src="https://github.com/user-attachments/assets/5b63b05a-24a1-4279-9efb-4da13e7a7603" />

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
With the use of Google Colab, I loaded the .csv file and initially inspected the whole sheet using the .info() where I found missing values from the columns. Since I found some blank cells, I assumed they have no data for it so I filled it out with "0". I also changed the data types on some columns and transformed the <i>district</i> and <i>sub_district</i> columns into its proper form. After that, I exported a transformed data into an .xlsx file.

## Excel
After initially inspecting and transforming the dataset through Google Colab (Python), I checked the whole file using Excel. Here are the following changes/manipulations I did using MS Excel.
1. Deleting all rows containing the "Off-Peak (00:00-17:00)" from the <i>time_window column</i>.
<br><img width="573" height="200" alt="8C781EA8-DFB1-4A74-8E11-E4815045CD84" src="https://github.com/user-attachments/assets/fcbed60b-4711-4efa-b21c-493bc6068967" /></br>
Since I've set the limitation of this Portfolio into "Peak Hours" only, I will not be needing the data from the "Off-Peak".
2. Double-checking the columns <i>district</i> and <i>sub_district</i>.
<br><img width="302" height="343" alt="C46CA56A-4BF6-4159-A4A0-E2D8850D976C" src="https://github.com/user-attachments/assets/9a686be1-f6eb-4c90-afba-ae434b6d6cd8" /></br>
I realized later while I was editing my dashboard <i>(whenever I click Talomo District, the Buhangin Area was always lingering at the topmost part of my Map visualization! I thought something was wrong with my map)</i> that the Buhangin Proper was grouped under "Talomo District". Had I not been a resident of this city, I wouldn't know that Buhangin Proper <b>should</b> have been under "Buhangin District" and so I changed in Excel.
3. Pivot Table
<br><img width="618" height="415" alt="4D119455-A894-4366-8866-5FA43C01438B" src="https://github.com/user-attachments/assets/59dec073-d21c-41e5-9d6f-93fd0bc952da" /></br>
<i><br>A little back story... lol</i></br>
I have a love-hate relationship with Pivot Table, to be honest, when I just first learned about it as a Team Leader. I didn't understood how to do it at first but when I figured out how it can make my life easy <i>(goodbye filters and sort!)</i>, I pushed harder to make it easy for myself.

Sure, it would be much easier for AI to make me a step-by-step instruction on how to build my own dashboard. But I figured that if I continued with it, I wouldn't even know how to explain the details and numbers on my dashboard. So I asked myself, <b>"In the years that I have been working in the Telecommunication industry, what were the usual questions they ask me during a meeting/report?"</b> This was how I started drafting Pivot Tables in Excel. 
# CONTINUE HERE #
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
## Month 1
1. <b>Identify the top worst-performing nodes.</b> ISP will now have to drill down the worst-performing nodes in the districts of Talomo, Buhangin and Poblacion.
2. <b>ISP to adjust bandwidth allocation.</b>
## Month 2
1. <b>Physical upgrade execution and migration.</b> Offload congested nodes to high-capacity FTTH infrastructure.
## Month 3
1. <b>Post-implementation impact analysis.</b> Latency should already be reduced to <20ms and peak bandwidth utilization is below 85%.
