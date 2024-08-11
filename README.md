<p align="center">
    <img src="Screenshot 2024-08-10 055333.png" alt="Car Ride Share System" Height="150",Width="750">
    <br />
</p>
<h2 align="center">Real-time Ride-Sharing Service</h2>

### Problem Statement and Requirements


**Business Requirements:**
- **Problem Definition:** Riksha aims to provide a real-time ride-sharing service that efficiently matches passengers with drivers, considering factors like location, traffic, and dynamic pricing.
- **Functionalities:**
  - Passenger registration and login.
  - Driver registration and approval process.
  - Ride request and matching algorithm.
  - Dynamic pricing based on demand and traffic.
  - Payment processing and receipt generation.
  - Real-time GPS tracking of rides.
  - Rating and feedback system for passengers and drivers.
- **Target Users:**
  - Passengers needing reliable and quick transportation.
  - Drivers looking to offer their services through a flexible platform.
- **Business Goals:**
  - Provide a scalable and reliable service.
  - Optimize operational costs while ensuring quality.
  - Maintain a high level of customer satisfaction.


**Non-Functional Requirements:**
- **Performance:**
  - Scalability to handle up to millions of users.
  - Response time under 2 seconds for critical operations.
- **Security:**
  - Authentication via OAuth2 for secure access.
  - Authorization based on roles (admin, driver, passenger).
  - Data encryption for all sensitive information.
- **Maintainability:**
  - Modular code structure to allow for easy updates and feature additions.
  - Comprehensive documentation and unit tests.
- **Additional Requirements:**
  - Compliance with local transportation regulations.
  - Integration with external services like Google Maps API.


### Use Case Diagram

We have eight main Actors in our system:

#### Actor Classification:
| Type      | Actor         | Goal Description                                                               |
|-----------|---------------|--------------------------------------------------------------------------------|
| **Primary** | Passenger     | Book a ride, make a payment, and rate the ride.                                 |
| **Primary** | Driver        | Accept a ride request, complete the ride, and receive payment.                    |
| **Primary** | Admin         | Manage system operations, users, and handle disputes.                            |
| **Supporting** | Payment Processor | Process payments, refunds, and handle transaction issues.                       |
| **Supporting** | GPS Service   | Provide real-time location data for route optimization and tracking.              |
| **Offstage** | Marketing Team | Analyze user data for targeted promotions and growth strategies.              |
| **Offstage** | Customer Support | Resolve passenger and driver issues, handle complaints, and provide assistance. |
| **Offstage** | Maintenance Team | Ensure the app and server infrastructure are functioning smoothly.               |


The top use cases of the Car Ride Share Service:
### 2. Use Case Names

1. **Request Ride** - Involves Passenger and Driver.
2. **Accept Ride** - Involves Passenger and Driver.
3. **Start the Ride** - Involves Passenger and Driver.
4. **End the Ride** - Involves Passenger and Driver.
5. **Verify Driver Info** - Involves Passenger and Driver.

#### Use Case Names:
1. **Request Ride** - Involves Passenger and Driver.
2. **Process Payment** - Involves Passenger and Payment Processor.
3. **Manage Ride** - Involves Driver and GPS Service.
4. **Rate The Ride*** - Involves Passenger.
5. **Provide Customer Support** - Involves Passenger, Driver, and Customer Support.

### Class Diagram

Here are the main classes of our Car Rental System:

   - **Classes:**
     - `User` (attributes: `userID`, `name`, `email`, `role`).
     - `Ride` (attributes: `rideID`, `status`, `price`).
     - `Vehicle` (attributes: `vehicleID`, `licensePlate`, `type`).
     - `Payment` (attributes: `paymentID`, `amount`, `method`).
     - `Route` (attributes: `routeID`, `startLocation`, `endLocation`).
     - `Feedback` (attributes: `feedbackID`, `rating`, `comments`).
- **User:** Attributes: userID, name, phoneNumber, email, userType (Driver/Passenger), location
- **Driver:** Attributes: driverID, licenseNumber, vehicleDetails, rating, status (Available/Unavailable)
- **Passenger:** Attributes: passengerID, paymentMethod, rideHistory
- **Ride:** Attributes: rideID, startLocation, endLocation, fare, rideStatus, route, timestamp
- **Vehicle:** Attributes: vehicleID, vehicleType, registrationNumber, capacity, driver
- **Payment:** Attributes: paymentID, amount, paymentMethod, status, transactionTimestamp
- **Route:** Attributes: routeID, startPoint, endPoint, waypoints, estimatedTime
- **Rating:** Attributes: ratingID, rideID, userID, score, feedback
- **Notification:** Attributes: notificationID, userID, message, timestamp
