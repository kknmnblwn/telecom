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
Although my strongest suit in data cleaning and manipulation was MS Excel, I realized that I <i>need</i> to do it with Python in Google Colab despite being intimidated with it at first.

I loaded the .csv file and initially inspected the whole sheet using the .info() where I found missing values from the columns. Since I found some blank cells, I assumed they have no data for it so I filled it out with "0". I also changed the data types on some columns and transformed the <i>district</i> and <i>sub_district</i> columns into its proper form. After that, I exported a transformed data into an .xlsx file.

## Excel
After initially inspecting and transforming the dataset through Google Colab (Python), I checked the whole file using Excel. Here are the following changes/manipulations I did using MS Excel.
1. Deleting all rows containing the "Off-Peak (00:00-17:00)" from the <i>time_window column</i>.
<br><img width="573" height="200" alt="8C781EA8-DFB1-4A74-8E11-E4815045CD84" src="https://github.com/user-attachments/assets/fcbed60b-4711-4efa-b21c-493bc6068967" /></br>
Since I've set the limitation of this Portfolio into "Peak Hours" only, I will not be needing the data from the "Off-Peak".
2. Double-checking the columns <i>district</i> and <i>sub_district</i>.
<br><img width="302" height="343" alt="C46CA56A-4BF6-4159-A4A0-E2D8850D976C" src="https://github.com/user-attachments/assets/9a686be1-f6eb-4c90-afba-ae434b6d6cd8" /></br>
I realized later while I was editing my dashboard <i>(whenever I click Talomo District, the Buhangin Area was always lingering at the topmost part of my Map visualization! I thought something was wrong with my map)</i> that the Buhangin Proper was grouped under "Talomo District". Had I not been a resident of this city, I wouldn't know that Buhangin Proper <b>should</b> have been under "Buhangin District" and so I changed it in Excel.
3. Finalizing the data per column.
<br>This is important to check since there were values in a column that wouldn't make sense. This was clearly overlooked when I did this file with Python. An example of this would be having a -99% packet loss and average latency (measured in milliseconds) of 9999.</br>
<img width="100" height="528" alt="169E8C5B-47CC-4852-BBC7-DB5F457300F5_4_5005_c" src="https://github.com/user-attachments/assets/b31c67b6-123f-4736-8f02-dd4a9f2dfd85" />

<img width="91" height="595" alt="19257C82-2C3D-4CD1-9B54-BF5A2782A8C1_4_5005_c" src="https://github.com/user-attachments/assets/ad355c28-51d9-4096-9874-2e43db745922" />

5. Pivot Table
<br><img width="618" height="415" alt="4D119455-A894-4366-8866-5FA43C01438B" src="https://github.com/user-attachments/assets/59dec073-d21c-41e5-9d6f-93fd0bc952da" /></br>
<i><br>A little back story... lol</i></br>
I have a love-hate relationship with Pivot Table, to be honest, when I just first learned about it in my previous role as a Team Leader. I didn't understood how to do it at first but when I figured out how it can make my life easy <i>(goodbye filters and sort!)</i>, I pushed harder to make it easy for myself. So this was the very foundation of how my Power BI dashboard came to be.

## Power BI
I used this tool for the data storytelling and in making the final dashboard. Sure, it would be much easier for AI to make me a step-by-step instruction on the contents of my own dashboard. But I figured that if I continued on with it, I wouldn't even know how to explain the details and numbers on my dashboard. So I asked myself, <b>"In the years that I have been working in the Telecommunication industry, what were the usual questions they ask me during a meeting/report?"</b>

# Key Insights
<br><img width="1200" height="655" alt="F2C5EF07-7D00-4B78-B3F0-F9A93651E4B1_1_105_c" src="https://github.com/user-attachments/assets/eb5afb2e-ec06-4abb-af8d-f08b384a1a82" />
In a span of three (3) years, a trend of increasing number in complaint tickets were noted across the seven (7) districts in Davao City.</br>

<br><img width="544" height="530" alt="39A41263-8EDD-480D-B577-FA20D82D48A1" src="https://github.com/user-attachments/assets/14ac4cb1-a0de-4e15-8617-af71da6263cb" />

Almost <b>90% of the existing technology used were a combination of Copper/VDSL and Fixed Wireless </b>which could be the main contributor to why the internet connection degrades during peak hours. </br>

<br><img width="966" height="520" alt="01B6668F-5055-4144-849A-A82DFEC4615C" src="https://github.com/user-attachments/assets/eae30f8b-5f2f-4400-ad1e-c59858c5bb72" />
When compared with the total Outage Duration (in milliseconds) per District, <b>Talomo and Buhangin Districts were consistently two of the highest. Ranking 3rd in the highest Outage Duration, yet, lower compared to the other districts in Complaint Tickets Logged is the Poblacion District.</b> Although <b>Agdao District is ranked 5th in Outage Duration, its Complaint Ticket Logged was the 3rd highest.</b></br>

<br><img width="1244" height="540" alt="4CE915A3-E2C9-4217-8F3F-5523179950DB" src="https://github.com/user-attachments/assets/c1885a4e-484b-4d5f-adc3-353784fa2a13" />
One of the contributors for these complaint tickets is the <b>Bandwidth Utilization (%)</b>. Having at least 85% BW Util means that the highway where cars (data) pass by from point A to B is 85% full!</br>

<br><img width="1240" height="524" alt="34C5043D-929F-46EB-AAF2-D17A4A954D4C" src="https://github.com/user-attachments/assets/932af68a-ae3f-47ef-9273-7d627d96627b" />
Continuing with the highway analogy, latency (measured in milliseconds) is the travel time of a single car to travel from your device to the destination server and back. <b>In this case, the districts Buhangin, Talomo and Poblacion experience the longest average latency.</b>
</br>

# Recommendations
## Month 1
1. <b>Identify the top worst-performing nodes.</b> ISP will now have to drill down the worst-performing nodes in the districts of Buhangin, Talomo and Poblacion.
2. <b>ISP to adjust bandwidth allocation.</b>
## Month 2
1. <b>Physical upgrade execution and migration.</b> Offload congested nodes to high-capacity FTTH infrastructure.
## Month 3
1. <b>Post-implementation impact analysis.</b> Latency should already be reduced to <30ms and peak bandwidth utilization is below 85%.
