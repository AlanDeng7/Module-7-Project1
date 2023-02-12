Chris Notes

• Pulling a sample population of 1000 restaurants from Toronto and Vancouver, which city has better rated restaurants? Comparing the distance of these restaurants to local landmarks (CN Tower for Toronto and Canada Place for Vancouver), does restaurant rating change as distance increases from the landmark? Yelp and Geoapify


Steps taken for data analysis
• Using Yelp Fusion API, pull a sample population of 1000 restaurants from Toronto and Vancouver
	• API allows for a 50 limit search, requiring the use of an offset to continue collecting data
	• API does not allow more than 1000 total searches within a set period of time
	• Save this in a CSV format for use within the group
• Using Geoapify API, use route function to calculate distance between each restaurant and that city's landmark
	• Landmarks chosen are CN Tower and Canada Place for Vancouver and Toronto respectively.
	• Convert latitude and longitude into a co-ordinate string that can be input to geoapify's API parameters list
	• Route directions are based on "middle optimized" driving distance, the most normal method between the restaurant and the landmark
	• Add the distance information to the Yelp API dataframe and save as another separate CSV 


Visualizations:

Histogram and box and whisker plot: This highlights the total number of restaurants that fall into specific rating bins in each city


• Yelp API only gives 1/2 star reviews without any in-between averages
• In general, the majority of restaurants in each city is 4 stars and above. From the data shown, Toronto has a larger number of 5 star rated restaurants compared to Vancouver, with Vancouver showing more 4.5 and 5 star restaurants compared to Toronto.
• Statistical Discussion: 
	• Even without normalization tests, it's pretty obvious that the data is not normally distributed, as most restaurants are heavily skewed above 4 stars
	• On first glance, the data seems to imply that a greater share of restaurants in Toronto are 5 stars compared to in Vancouver, which has a greater share of 3.5 to 4.5 star restaurants. However when plotted as a box and whisker diagram, both boxes (median and mean) and the whiskers are the same and both imply that potential outliers consist of restaurants below 3.5 stars rating, showing that there is very little statistical difference in restaurant ratings between the two cities. 
	• It is currently unknown how Yelp chooses which restaurants to return for the search queries (i. .e "Toronto" "Restaurant"). The data is not seemingly randomized as multiple searches of the database seems to return the exact same results. There could be implicit bias in the sample population as it is predicated on what Yelp decides to feature for the queries, and it could be that more heavily favored restaurants with high review scores tend to feature strongly. This would create bias in the data compared  to a random sampling of restaurants. 

Box and Whisker Plot
	• When viewed as a box and whisker plot, the Toronto and Vancouver ratings are identical, with the number of outliers determined as 3 stars and below. This further supports that on average, the restaurant ratings for both cities is very close.

	Scatterplots: This highlights restaurant ratings vs. distance from local landmark

Scatterplots: This highlights the driving distance from a local landmark in each city to each restaurant from the Yelp API data pull. For Toronto, the landmark is the CN tower whereas for Vancouver it's Canada place.
	• It can be seen that most restaurants are heavily clustered close to the landmark.
		○ Could be indicative that more restaurants exist near landmark tourist attractions, or simply because these landmarks are close to city center and that is where the sampling from Yelp originates given the keyword search terms.
	• Both R-squared values and Pearson correlation shows that there is very weak/non-existent correlation between restaurant distance and rating
		○ This implies that either restaurant quality throughout each city is good, or that the sampling from Yelp is biased towards suggesting highly rated restaurants with no regard to distances
		
