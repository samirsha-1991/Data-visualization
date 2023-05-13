# Data visualization and exploration for ChrisCo 

## 1.	Introduction to data visualization

Data refers to a collection of individual values that convey a meaning, once it is processed (Techterms.com, 2019).  Data visualization is the process of  graphically representing the data and information by using elements as graphs, charts, plots and maps (Tableau, 2020). Usually humans are not good at interpreting and extracting useful information after analyzing a large amount of data like what machines normally do. The best option for this is the visual interpretation of data  (Döbler and Grössmann, 2019). 
With the exponential growth of data in various fields, data visualization has become a critical requirement as it can help analysts, data scientists and every decision maker in below areas
1.	Understanding complex data easily using visualizations
2.	Identify trends, seasonality, outliers and patterns from data
3.	Storytelling using dashboards and animations 
4.	Data exploration through interactive visualizations (Döbler and Grössmann, 2019).
In creating effective data visualizations there are few key things to be considered. It involves a thorough understanding on the data to be analyzed and data analysis principles, choosing the most appropriate visualization methods to illustrate accurately the underlying meaning of data to the users and finally well presenting the visualization to the reader including correct naming, labeling, color matching  and formatting. 
Overall data visualization is  powerful tool in interpreting data in a human readable and understandable versions and aid in making accurate data driven decisions. 
 
## 2.	Discussion 

This report contains a detailed discussion about a visual data exploration done about the performance of 45 outlets at the company ChrisCo which can be used for making data driven decision by the company. The analysed dataset contains below information
1.	Daily number of customer visits to each of the company's outlets
2.	Total annual spend on local marketing for each outlet (£)
3.	Total annual cost of overheads for each outlet (£)
4.	Size (floor space) in meters squared for each outlet
5.	Total number of full-time staff employed at each outlet

### 2.1 Segmenting the outlets considering their annual customer visits.

For the convenience of analysis, all the 45 outlets are segmented into 3 main categories High, Medium and Low depending on the total annual volume of customers visited each outlet (referred as customer volume hereafter) visiting each outlet. The below bar chart in Figure 1, depicts a visual representation of the customer volume to each of the outlet during year 2021. Since bar chart is a good visualization option in comparing frequency of occurrence or count per each category for selected discrete variables, this can be used for a quick and easy comparison among the customer volumes per each outlet and to segment them accordingly to the given categories. Doing this visually is better and easier than going for statistical methods in finding high and low margins. 

 ![image](https://github.com/samirsha-1991/Data-visualization/assets/131381690/92f01434-3944-47e2-9ce8-19ac3a187a8c)

 
Figure 1: Segmentation of outlets based on total annual customer arrivals
As per the Figure 1, the 3 outlets ‘RAN’, ‘RFY’ and ‘DMN’ which records the highest annual customer visits (more than 600K) are categorized under category ‘High Volume’ while outlets ‘DSA’,’EYS’,EEC’,’BMF’, ‘BSQ’, ‘CGV’ and ‘CYK’ are put into the ‘Medium category’ (200K< customer volume <400K)   and the rest of the 35 outlets are categorized as ‘Low volume’ outlets which record customers visits under 200K. 

### 2.2 Analyzing the factors impacting for the volume of customers

Below Figure 2 shows the correlation heatmap which depicts the linear relationship between each variable couple in the dataset. A strong positive correlation (in which both the 2 variables shows the same pattern, both increasing/both decreasing) is indicated by a high coefficient value close to 1 in the heatmap, while a strong negative correlation (in which 2 variables shows contrasting patterns one increasing other decreasing vice versa) is indicated by a low coefficient value close to -1. The variables with low correlation (no relation between the 2)  are indicated by values close to 0. Hence correlation heat map is a good way in identifying what variables have significant relationships with the customer volume. The color selection process is optimized to facilitate the easy identification of significant correlations.. By identifying the key variables and understanding their relationship to the Annual customer volume, it is possible to optimize these variables to increase customer volume. 

![image](https://github.com/samirsha-1991/Data-visualization/assets/131381690/a7df785f-5c33-4c2f-a891-0d437f4e3c10)

Figure 2 : Correlation heatmap of the variables

As per the Figure 2, it can be clearly observed that there is a significant impact of the 3 variables marketing expenditure, size and staff to the customer volume of the outlet with all correlation coefficients above 0.9. Hence to increase customer volumes these 3 variables should be increased in the outlets. Taking Marketing expenditure only into account it has an extremely high positive impact towards the customer volume. In contrast, the customer volume  has almost no relation with the ‘Overheads (£)’ variable. To be more specific, it is possible to reduce overhead expenditure of high overhead outlets while maintaining the customer volume.  But there is a significant impact if reduced too much which will be discussed in section 2.4.

### 2.3 Analysing for outliers

The interactive bubble plot in Figure 3 shows the point distribution between variables outlet size, customer volume where size of the bubble displays the overhead expenditure. In section 2.2 it was identified that outlet size has a high positive impact to the customer volume and overheads almost has no impact. From the below bubble chart, it is much easier to identify the outlets which deviate from the above conclusion.  The colors are helpful in identifying and comparing outlets in each category. In particular, the size of the bubbles allows to identify any high or low-overhead locations and to relate them with volume and size of outlet , which can be further explored to understand why some outliers exist. (right most figure shows  a zoomed version of leftmost figure)
 
 ![image](https://github.com/samirsha-1991/Data-visualization/assets/131381690/dcd2f341-6ce6-486c-8151-3ab952540ff2)


Figure 3: Analysing outliers

According to the above Figure 3, it can be observed that in most of the outlets the customer volume is high when the outlet size is high and vice versa. But there are few outlets that appear to defy this trend. Comparing outlets ‘DMN’ and ‘RFY’ with ‘RAN’ all the 3 outlets have roughly the same customer volume but the ‘DMN’ and ‘RFY’ outlets size much lower than ‘RAN’. The same behavior can be observed in medium  outlets like ‘DSA’ compared with ‘BSQ’.  When considering the bubble size or the overheads, in outlet RFY the overhead is much lower but still the customer volume ins high. These outliers can be investigated further to identify potential reasons for their unexpected performance, such as the impact from location, customer demographics, or the presence of unique features.



### 2.4 Analyzing the trend of customer visits to the outlets

Up to now what was analyzed is the factors impacting sum of annual customers arrived to each outlet. But analyzing only the volume is not sufficient since it does not convey any idea on the outlets which are attracting new customers and outlets where there are customer churns. For this, there is another key performance metric which needs to be considered which is the trend of customer volume (referred to as volume trend hereafter) 
Line charts are effective at identifying time series data like customer volume, as they display data points connected by lines. Plotting time on the x-axis and the variable being measured on the y-axis allows patterns and trends in the data over time to be easily seen and analyzed. In Figure 3, line chart at the leftmost side shows variation of the 14 day moving window average (to smooth short-term fluctuations) overlaid with trendline. Specifically, radar plots are well-suited to analyzing multivariate data where each variable shares a similar scale or unit of measurement. Hence the 2 overlaid radar plots are used to demonstrate how other variables  normalized to Marketing (£) differ per outlet in the context of separate positive and negative volume trends. These two plots provide an effective means of comprehending the factors that contribute to certain outlets being more successful in attracting customers.

![image](https://github.com/samirsha-1991/Data-visualization/assets/131381690/5d4f84fe-11e4-4e1d-8bf6-8e2355c2d199)

Figure 4: Analysing customer volume trend and factors effecting

As Figure 4 line chart shows, the outlets DSA shows a significantly steeper incline indicating a higher attraction of customers compared to outlets BMF, BSQ and CGV. But in contrast outlets  EYS, EEC and CYK are losing their customers at similar rates. Comparing the 2 radar plots separately drawn for positive and negative trending outlets it can be observed that there seems a little significance from the overhead expenditure to the difference. To confirm that this is the underlying cause for the customer  churn additional factors and KPIs needs to be analyzed. Possible cause would be when the company reduces its overhead costs at the expense of customer service quality, it may lead to customer dissatisfaction and ultimately churn 


### 2.5 Analyzing on the newly opened and recently closed outlets 

From the data it can be observed that 6 outlets 'YMQ', 'XSB', 'AGN', 'AYD', 'ZSJ' and 'ZMY' are recently opened while 5 outlets 'IZX', 'YGE', 'HTF', 'HNV' and 'ZYT' are closed by the company. 
To understand whether closing 5 outlets have caused any significant customer loss to the company and has it being recovered by the newly opened 6 outlets, an area plot can be used. Area plots can be used to show how customer volume has changed over time for opened and closed outlets. They are similar to line charts, but instead of just showing the data points connected by lines, the area between the x-axis and the line is filled in with color, creating a shaded area that emphasizes the magnitude of change. By stacking data points on top of each other, possible to easily see how the composition of the data changes over time along with what has happed to the total volume. 

![image](https://github.com/samirsha-1991/Data-visualization/assets/131381690/090b2f18-a835-46a7-be00-77e1d23c0a93)


Figure 5: Customer volume variation of newly opened and closed outlets
As per the above Figure 5, it can be observed that there is no impact to the net total customer count and the customer count lost by closing the 5 outlets has being recovered from the new outlets. And the new customer volume has become higher than the previous total with the opening of outlet ZMY. Currently the average volume of customers handled by closed outlets seems much higher than that of new outlets but according to the chart it can be seen that the new outlets are increasing their customer volumes which will be analysed again in section 2.6. 


### 2.6 Analyzing the customer growth factor of all the outlets

The below bubble plot in Figure 6 provides a quick and intuitive view on which outlets are experiencing the highest growth rates and which ones are struggling or experiencing customer churns. By using the bubble plot, possible to clearly see the relationship between the outlet names, the customer volume trend, and the total customer volume per annum and it allows to compare the daily customer volume trends and total customer volume per annum for different outlet categories in a single view using different colors. The use of bubbles instead of traditional markers allows to incorporate a third variable, the total customer volume per annum where the bubble size conveys the relative magnitude of the total customer volume per annum for each outlet

![image](https://github.com/samirsha-1991/Data-visualization/assets/131381690/423ed9fd-fe55-49e8-9335-d56e8176997a)

Figure 6: Rate of change of customer volume

As per the above Figure 6, it can be seen that the best performing outlet is the ‘RAN’ which has the highest growth rate and the largest customer base. Following that, all the recently opened outlets are showing high growth factors even their current customer base is small. Also there are some outlets specially 2 high volume outlets and 3 medium outlets which are experiencing significant customer churns for which the company should pay more attention and take precautions. Overall, there are only few outlets which are performing well, but most of the outlets are having negative growth or almost zero growth factors which is a risk factor to the company.


### 2.7 Analyzing on the newly opened and recently closed outlets 

As discussed in section 2.5 it could be observed that with the opening of 6 new outlets after closing 5 outlets has not made a significant impact to the total customer count of the company. But it is worth to analyze the impact of this on the aspect of other variables as well. 
Bar charts are a common and effective way of displaying and comparing discrete data values. They allow for the clear visualization of differences between values, making them an ideal choice for comparing normalized data, such as the variable values of newly opened and recently closed outlets. Since the number of days these outlets remain open may vary, comparing the total variable values per annum would be inaccurate. By normalizing the data to the number of days each outlet was open, the bar chart allows for an accurate comparison of the relative performance of each outlet. Here 5 separate bar charts (including separate bar for newly opened and recently closed outlet) are drawn to the 5 variables. 

![image](https://github.com/samirsha-1991/Data-visualization/assets/131381690/04cf0fbc-66ce-4128-8ddc-3b3c9fe82333)

Figure 7: Per day variable value for newly opened and recently closed outlets

As per the above Figure 7, it can be seen that the there is a small gap between the number of average customers arriving to a new outlet when compared to that of a closed outlet. But from this observation it cannot be exactly said that new outlets are not performing well since according to Figure 5 it seems that this number is gradually increasing and need to analyze again after some time duration. Other than customer count such significant difference can be observed in the average staff and Overheads. The per outlet overhead expenditure and staff count is much higher in new outlets while they are carrying a lesser amount of customer volume than the closed outlets. This may lead to an additional cost burden to the company and needs to be optimized to earn more profits while retaining the customer base. 

### 2.8 Analyzing the seasonality of the customer arrivals for outlets

The below interactive line chart in Figure 8 shows the weekly seasonality (means that certain days of the week exhibit similar patterns in data over time)  in customer arrivals for outlets “EEC” and “CYK”.  This information is particularly relevant for understanding customer behavior and optimizing staffing and other resources to meet demand. Using the visualization it is possible to identify the specific dates in which the customer arrivals are highest and adjust operations accordingly. Also the stakeholders can use the tools like hover, zoom and pan to analyse complex data in a clear and engaging way. 

![image](https://github.com/samirsha-1991/Data-visualization/assets/131381690/8dc0e2f0-bc63-4d22-9b87-86c2088a7e9d)

Figure 8: Seasonality in the customer arrivals to outlets

As per the above Figure 8, it can be observed that both outlets experience a significant increase in customer arrivals on certain days of the week. Example a peak in customer arrivals can be observed in 2021-01-08 (Friday) and drop in 2021-01-11 (Monday) for both the outlets .This pattern is consistent over time and suggests that customers are more likely to visit these outlets on Fridays of every week and in contrast to that in Mondays customer arrivals are much low. By using this insight, it is possible to optimize the operations to meet demand, potentially improving customer satisfaction. 



## Conclusion

Few conclusion drawn from the total analysis
•	There is a positive impact from the amount spent on local marketing, outlet floor size and number of full time staff to achieve a high volume of customers for an outlet. 
•	There are some outlets which deviate from the above behavior and further investigation could reveal potential opportunities for improving performance or identifying areas for cost savings.
•	Few outlets are there in which the customer volume is increasing while most of the outlets are having negative growth or almost zero growth factors which is a risk factor to the company. 
•	Newly opened outlets have higher variable costs than recently closed outlets, suggesting that the company may want to focus on reducing costs in new locations. But can observe that the customer volume of new outlets are expanding at a high rate. 
•	Peak in customer visits can  be observed in outlets “EEC” and “CYK” every Fridays and in Mondays customer arrivals are much low. Company may optimize the operations to meet demand, potentially improving customer satisfaction.
Overall, these insights can be used to for the purpose of data driven decision-making and improve the overall performance of the outlets. 


