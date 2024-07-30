# Travel-And-Hotel-Analysis

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


![Screenshot (302)](https://github.com/user-attachments/assets/8671b9d5-4779-41e1-a622-e52135d12ec6)
![Screenshot (303)](https://github.com/user-attachments/assets/1deaad4d-de6e-490f-bef2-ba4ec3ee1900)
![Screenshot (305)](https://github.com/user-attachments/assets/c7fc3144-da77-4e2c-abc8-b03bffd5c6f7)
