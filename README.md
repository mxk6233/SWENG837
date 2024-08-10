<p align="center">
    <img src="Screenshot 2024-08-10 055333.png" alt="Car Ride Share System" Height="150",Width="750">
    <br />
</p>
<h2 align="center">Real-time Ride-Sharing Service</h2>

**Document Overview:**

* [System Requirements](#system-requirements)
* [Use Case Diagram](#use-case-diagram)
* [Class Diagram](#class-diagram)
* [Activity Diagrams](#activity-diagrams)

A Car Ride Sharing System is a software built to handle the 

### System Requirements

The following set of requirements for the Ride Sharing Service

1. 

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

Here are the top use cases of the Car Ride Share Service:

#### Use Case Names:
1. **Request Ride** - Involves Passenger and Driver.
2. **Process Payment** - Involves Passenger and Payment Processor.
3. **Manage Ride** - Involves Driver and GPS Service.
4. **Administer System** - Involves Admin.
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
