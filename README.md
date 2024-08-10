<p align="center">
    <img src="Screenshot 2024-08-10 055333.png" alt="Car Ride Share System" Height="200",Width="800">
    <br />
</p>

<h3 align="center">Real-time Ride-Sharing Service</h3>

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



This criterion is linked to a Learning OutcomeProblem Statement and Requirements
This criterion is linked to a Learning OutcomeUML Case Diagram
UML Domain Model
This criterion is linked to a Learning Outcome
UML Sequence Diagram
This criterion is linked to a Learning OutcomeUML State Diagram
This criterion is linked to a Learning OutcomUML Component Diagram
eUML Activity Diagram
Cloud Deployment Diagram
Skeleton Classes
Design Patterns


Motivation



System Requirements

Use Case Diagram
We have four main Actors in our system:

Here are the top use cases of the 

Class Diagram
Here are the main classes of our

Stack
Summary of what the stack looks like now including a picture with the core tech:

Back-end
Back-end services that makes up the Serverless Airline functionalities as of now:

Service	Language	Description
Front-end
