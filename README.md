
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

![Screenshot (308) - Copy](https://github.com/user-attachments/assets/5838224f-821f-4ad1-8384-d962692ec80d)

#### Calculate total number of flights:          
         total_no_of_flights = COUNT(flights[travelCode])

 ![Screenshot (304) - Copy](https://github.com/user-attachments/assets/927fd4d2-b485-43d3-909f-a0ca7419d7fb)

#### Calculate total number of users: 
         total_no_of_customers = DISTINCTCOUNT(flights[userCode])

![Screenshot (306) - Copy](https://github.com/user-attachments/assets/aeda306e-b6cb-4873-a248-022676699285)

#### Calculate total revenue of flights:          
         Total_revenue_of_flight = SUM(flights[price])

![Screenshot (305) - Copy](https://github.com/user-attachments/assets/147a9c2d-c549-43b6-b506-1e1730dd8c3c)

#### Calculate different number of hotels: 
         Hotels = DISTINCTCOUNT(hotels[hotelname])

![Screenshot (314) - Copy](https://github.com/user-attachments/assets/9d8e9141-c109-41e3-9ad1-62205d5b8fe3)

#### Calculate total revenue of holes: 
         Total_revenue_of_hotels = SUM(hotels[total])

![Screenshot (312) - Copy](https://github.com/user-attachments/assets/1809bd63-338a-4d92-ae89-bee3493669b7)

#### Calculate different number of companies: 
         Companies = DISTINCTCOUNT(users[company])

![Screenshot (313) - Copy](https://github.com/user-attachments/assets/8121b984-9c2d-4332-bf8f-a78d75a178d9)

### Key Insights

- Flying Drop (38758) has a considerably lower number of flights compared to Cloudify (116378) and Rainbow (116752). This discrepancy can be attributed to the fact that Flying Drop exclusively offers first-class flights, which inherently limits its service to a niche market segment.

![Screenshot (306)](https://github.com/user-attachments/assets/07fd72c6-c7d4-41f1-80d5-b3a7ce49db2b)
  
- Upon analyzing the relationship between flight distance and pricing, it is evident that there is no consistent pattern of price increase with increasing distance. The data reveals that while some longer flights are indeed more expensive, there are numerous instances where prices do not increase proportionally with distance. In fact, at certain points, the prices actually decrease as the distance increases.
  
![Screenshot (311) - Copy](https://github.com/user-attachments/assets/728739d1-1664-4173-9474-ea2ab3eb60ec)

- This analysis indicates that the year 2020 experienced the highest number of flights (112571) compared to other years in the dataset. This peak in flight volume highlights a significant operational activity for that year.
  
![Screenshot (310) - Copy](https://github.com/user-attachments/assets/26ccb056-0a5d-4a1b-9609-04c05a343b38)

- the top three flight destinations based on the number of flights Florianopolis (SC): 57,317 flights, Aracaju (SE): 37,224 flights and Campo Grande (MS): 34,748 flights. And The destination which has least number of flights is Rio de Janeiro (RJ): 16815
  
![Screenshot (309) - Copy](https://github.com/user-attachments/assets/aaaa3748-9497-4a25-85c0-3b77171b20fe)

- Our analysis over the past five years indicates that Hotel K has consistently hosted the largest number of customers (5094), followed by Hotel CB with 5,029 customers and Hotel BD with 4,829 customers. In contrast, Hotel A has the least number of customers, totaling 3,330. This lower volume may be attributed to Hotel A's higher pricing compared to the other hotels.
  
![Screenshot (315) - Copy](https://github.com/user-attachments/assets/573f34e7-ad62-46e9-ac01-5265d283858f)
![Screenshot (316) - Copy](https://github.com/user-attachments/assets/ae750e02-027f-46f4-b759-ddc71bddcf80)

- Our analysis indicates that Company 4You is utilized by a significant number of customers, with a total of 453 customers. This highlights Company 4You's strong appeal and customer base.
  
![Screenshot (317) - Copy](https://github.com/user-attachments/assets/e3bb982a-ca2a-42e4-aef1-c65e8c5bc5a4)

# Report Snapshot (Power BI DESKTOP)

![Screenshot (309)](https://github.com/user-attachments/assets/12d7bc1a-2dee-49f3-9525-dec7bc90b34e)
![Screenshot (308)](https://github.com/user-attachments/assets/95874b61-6595-4b76-a871-035b63377d7c)
![Screenshot (305)](https://github.com/user-attachments/assets/c7fc3144-da77-4e2c-abc8-b03bffd5c6f7)
