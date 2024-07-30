![image](https://github.com/user-attachments/assets/8d336d0c-a176-4f51-b951-039e08c7c791)# Travel-And-Hotel-Analysis

### Objective-
Argo Solutions, A leading technology company in Latin America, developing solutions to facilitate expense management and corporate travel using technology as an enabler of these processes. ​This is a dataset focusing on flights and hotels.
Objective is to analyze this set with over one thousand users and 250 thousand travels to produce insights. And find How can Argo offer the best travel experience for its customers?

### Features
- Overview Dashboard: A high-level summary of key travel metrics including total expenses, number of trips, and top destinations.
- Charts and Graphs: Various visualizations including bar charts, pie charts, line graphs, and area charts to display data trends and comparisons.
- Maps: Geographical maps to show hotels locations.
- Category Filters: Slicers to filter by categories such as years.
- KPIs: Display key metrics such as total number of trip, total revenue of flights, total agencies, total flight type, company type.
- DAX : Calculated columns and measures.

### Calculate Columns

#### Converting ages into age range: 

             age_range = if(AND(users[age]>21, users[age]<30), "21-30", 
    if(AND(users[age]>31, users[age]<40), "31-40",
    if(AND(users[age]>41, users[age]<50), "41-50",
    if(AND(users[age]>51, users[age]<60), "51-60",
    if(AND(users[age]>61, users[age]<70), "61-70",
    if(AND(users[age]>71, users[age]<80), "71-80","81-90"
    ))))))

#### Route tells that customers travel from one city to another: 

             route = CONCATENATE([travelfrom - Copy.2.1] & " - ",  [travelto - Copy.2.1])

### Calculate Measures

#### Calculate Average price of Flights: 
         average_price = AVERAGE(flights[price])

#### Calculate number of flight types:          
         Flight_Type = DISTINCTCOUNT(flights[flightType])

#### Calculate total number of flights:          
         total_no_of_flights = COUNT(flights[travelCode])

#### Calculate total number of users: 
         total_no_of_customers = DISTINCTCOUNT(flights[userCode])

#### Calculate total revenue of flights:          
         Total_revenue_of_flight = SUM(flights[price])

#### Calculate different number of hotels: 
         Hotels = DISTINCTCOUNT(hotels[hotelname])

#### Calculate total revenue of holes: 
         Total_revenue_of_hotels = SUM(hotels[total])

#### Calculate different number of companies: 
         Companies = DISTINCTCOUNT(users[company])

### Key Insights

- Flying Drop (38758) has a considerably lower number of flights compared to Cloudify (116378) and Rainbow (116752). This discrepancy can be attributed to the fact that Flying Drop exclusively offers first-class flights, which inherently limits its service to a niche market segment.
- Upon analyzing the relationship between flight distance and pricing, it is evident that there is no consistent pattern of price increase with increasing distance. The data reveals that while some longer flights are indeed more expensive, there are numerous instances where prices do not increase proportionally with distance. In fact, at certain points, the prices actually decrease as the distance increases
- This analysis indicates that the year 2020 experienced the highest number of flights (112571) compared to other years in the dataset. This peak in flight volume highlights a significant operational activity for that year.
- the top three flight destinations based on the number of flights Florianopolis (SC): 57,317 flights, Aracaju (SE): 37,224 flights and Campo Grande (MS): 34,748 flights. And The destination which has least number of flights is Rio de Janeiro (RJ): 16815
- Our analysis over the past five years indicates that Hotel K has consistently hosted the largest number of customers (5094), followed by Hotel CB with 5,029 customers and Hotel BD with 4,829 customers. In contrast, Hotel A has the least number of customers, totaling 3,330. This lower volume may be attributed to Hotel A's higher pricing compared to the other hotels.
- 


![Screenshot (302)](https://github.com/user-attachments/assets/8671b9d5-4779-41e1-a622-e52135d12ec6)
![Screenshot (303)](https://github.com/user-attachments/assets/1deaad4d-de6e-490f-bef2-ba4ec3ee1900)
![Screenshot (305)](https://github.com/user-attachments/assets/c7fc3144-da77-4e2c-abc8-b03bffd5c6f7)
