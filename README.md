# Davao City Internet Service: Peak-Hour Analysis
<img width="2502" height="1352" alt="F10F46A6-13C6-47CD-AAE0-27391D645220" src="https://github.com/user-attachments/assets/5b63b05a-24a1-4279-9efb-4da13e7a7603" />

# Project Summary
This project studies the peak-hour internet service (IS) performance in the most populated districts in Davao City. This aims to aide our local internet service providers (ISPs) to repurpose, if needed, their upgrade budget allocation.

# Problem Statement
Identify high-stress geographic service areas in Davao City experiencing network reliability issues during peak hours (6:00 PM – 11:00 PM) to minimize customer churn and optimize capital allocation for infrastructure upgrades.

# Data
The data was derived through the Prompt Engineering. Here's my prompt using Google Gemini.

><i>I am an aspiring Data Analyst and I want to make a portfolio with a Problem Statement below but I need a raw data (at least 3years) that needs to be cleaned up and manipulated. Generate one and make it into a downloadable .csv file.
"Which geographic clusters in Davao City suffer from the highest network degradation during peak hours (6 PM – 11 PM), and which sub-districts should be prioritized for Fiber-to-the-Home (FTTH) infrastructure upgrades?”</i>

# Methodology
## Python
Although my strongest suit in data cleaning and manipulation was MS Excel, I realized that I <i>need</i> to do it with Python in Google Colab despite being intimidated with it at first.

<br><img width="2722" height="1284" alt="908FCB5E-D096-4F3B-A731-F490A8C9C76B" src="https://github.com/user-attachments/assets/60c0f0e6-002d-4bfc-bb8d-d33d9692d9db" /></br>
I loaded the .csv file and initially inspected the whole sheet using the .info().

<br><img width="2726" height="1312" alt="063E4563-B8BB-4133-9A3E-933D7D235B69" src="https://github.com/user-attachments/assets/5c352ce0-7c19-4ff1-894e-ae2cc29c638e" /></br>
I've initially checked the data types and decided whether it's correct. Having observed that the <i>log_date</i> was set as an <i>object</i>, I changed it into <i>datetime</i> data type. There had been a couple of instances throughout my data cleaning and manipulation that I have set the proper data type for a column.

<br><img width="2746" height="1026" alt="4B17DCF9-451B-413D-AA8D-E21F300737F1" src="https://github.com/user-attachments/assets/5827655f-c2fd-414e-9233-775db3d838f2" /></br>
Since I have limited my project into the "Peak (18:00-23:00)" only, I filtered out of the file rows with values "Off-Peak (00:00-17:00)" from the <i>time_window</i> column. This has reduced the number of rows <b>from 26,280 to 13,795</b>.

<br><img width="2746" height="1138" alt="CE660E8F-81AA-418B-BFD5-C45EC0C61954" src="https://github.com/user-attachments/assets/79afe7a1-ce8e-43d7-8623-beddf6195065" />
<img width="2722" height="1342" alt="84AB748A-B707-4F3F-A93E-93E6529811A0" src="https://github.com/user-attachments/assets/e583820b-fa3c-45e9-9649-f510e10db1d1" /></br>
For the <i>packet_loss_pct</i> column, I inspected the whole column with <i>.describe()</i> which helped me check important values contained within that column. With it, I found out that there were <b>values with -99.00</b> which might be due to a glitch in the sensor. By knowing the average packet loss, I <b>replaced the negative values with 4.25 (average packet loss value)</b> while retaining all other values within that column.

<br><img width="2722" height="1344" alt="0864F5CB-0F21-4309-A68E-A8E7510EA7A3_1_201_a" src="https://github.com/user-attachments/assets/0b737b7b-fd71-42b0-9028-6476a84cb8bc" /></br>
For the columns <i>district</i> and <i>sub_district</i>, I set the values into a <b>proper noun</b>. With the help of Google Gemini, I found out that the equivalent of <i><b>=PROPER(cell)</i></b> in Excel is <i><b>.str.title()</i></b>. So I then made sure to check the unique values with the <i>Print()</i> function.

After transforming the values in both columns in the dataset, I proceeded to sort the <i>sub_district</i> according to its <i>district</i>. We can see in the highlighted box that <b>a part of the Buhangin Proper was labeled under Talomo District</b>.

To correct this error, I <b>renamed the values with Talomo District to Buhangin.</b> To double check if there's still some mislabeled district, I used the code <i>df.groupby('district')['sub_district'].unique().to_frame()</i> to help me check.
<img width="2732" height="838" alt="9CF7FD6F-1D5B-49E5-878C-032FC8BA4333" src="https://github.com/user-attachments/assets/56b37e94-006b-4be1-b79d-6974d4f1474a" />


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
