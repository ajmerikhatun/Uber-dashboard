# 🚕 Uber Data Analysis - SQL Questions (PostgreSQL)

This document contains SQL queries solved using PostgreSQL for the Uber Data Analysis case study. Each query answers a specific business question and provides insights to support decision-making.

---

## 📌 1. Retrieve all successful bookings
```sql
SELECT * FROM bookings
WHERE booking_status = 'Success';
```

✅ Insight: Filtered out all bookings with a status of 'Success' to analyze completed rides.

📌 2. Find the average ride distance for each vehicle type
```sql
SELECT vehicle_type, AVG(ride_distance) AS avg_distance 
FROM bookings
GROUP BY vehicle_type;
```

✅ Insight: Calculated average ride distances across all vehicle types to compare their usage patterns.

📌 3. Get the total number of canceled rides by customers
```sql
SELECT COUNT(*) 
FROM bookings
WHERE booking_status = 'Canceled by Customer';
```

✅ Insight: Found the total count of rides canceled directly by customers.

📌 4. List the top 5 customers who booked the highest number of rides
```sql
SELECT customer_id, COUNT(*) AS total_rides
FROM bookings
GROUP BY customer_id
ORDER BY total_rides DESC
LIMIT 5;
```

✅ Insight: Identified the top 5 most active customers based on their booking frequency.

📌 5. Get the number of rides canceled by drivers due to personal and car-related issues
```sql
SELECT COUNT(*) AS rides_canceled
FROM bookings
WHERE canceled_rides_by_driver = 'Personal & Car related issue';
```

✅ Insight: Found how many rides were canceled by drivers for personal or vehicle-related reasons.

📌 6. Find the maximum and minimum driver ratings for Go Sedan bookings
```sql
SELECT MAX(driver_ratings) AS max_rating,
       MIN(driver_ratings) AS min_ratings 
FROM bookings
WHERE vehicle_type = 'Go Sedan';
```

✅ Insight: Analyzed driver ratings specific to the 'Go Sedan' vehicle type.

📌 7. Retrieve all rides where payment was made using UPI
```sql
SELECT * FROM bookings 
WHERE payment_method = 'UPI';
```

✅ Insight: Pulled all rides paid for via UPI for payment method analysis.

📌 8. Find the average customer rating per vehicle type
```sql
SELECT vehicle_type, AVG(customer_rating) AS avg_rating
FROM bookings
GROUP BY vehicle_type;
```

✅ Insight: Calculated average customer ratings for each vehicle type to assess service quality.

📌 9. Calculate the total booking value of rides completed successfully
```sql
SELECT SUM(booking_value) AS total_booking_value 
FROM bookings
WHERE booking_status = 'Success';
```

✅ Insight: Found the total revenue generated from successfully completed rides.

📌 10. List all incomplete rides along with the reason
```sql
SELECT booking_id, incomplete_rides_reason
FROM bookings
WHERE incomplete_rides = 'Yes';
```

✅ Insight: Retrieved all rides that were incomplete, with the specific reason for each.

### 🛠 Tools Used
- PostgreSQL (for query execution)
- pgAdmin (for database management)


👩‍💻 Created by: Ajmeri Khatun

📅 Date: July 2025


