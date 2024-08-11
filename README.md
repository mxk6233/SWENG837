<p align="center">
    <img src="Screenshot 2024-08-10 055333.png" alt="Car Ride Share System" Height="150",Width="750">
    <br />
</p>
<h2 align="center">Real-time Ride-Sharing Service</h2>

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

### Use Case Diagram:

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

### Use Case Names:

- **Request Ride** - Involves Passenger and Driver.
- **Accept Ride** - Involves Passenger and Driver.
- **Start the Ride** - Involves Passenger and Driver.
- **Rate The Ride** - Involves Passenger.
- **Verify Driver Info** - Involves Passenger and Driver.
- **Provide Customer Support** - Involves Passenger, Driver, and Customer Support.

### Classes

- **User:** Attributes: `userID`, `name`, `phoneNumber`, `email`, `userType` (Driver/Passenger), `location`
- **Driver:** Attributes: `driverID`, `licenseNumber`, `vehicleDetails`, `rating`, `status` (Available/Unavailable)
- **Passenger:** Attributes: `passengerID`, `paymentMethod`, `rideHistory`
- **Ride:** Attributes: `rideID`, `startLocation`, `endLocation`, `fare`, `rideStatus`, `route`, `timestamp`
- **Vehicle:** Attributes: `vehicleID`, `vehicleType`, `registrationNumber`, `capacity`, `driver`
- **Payment:** Attributes: `paymentID`, `amount`, `paymentMethod`, `status`, `transactionTimestamp`
- **Route:** Attributes: `routeID`, `startPoint`, `endPoint`, `waypoints`, `estimatedTime`
- **Rating:** Attributes: `ratingID`, `rideID`, `userID`, `score`, `feedback`
- **Notification:** Attributes: `notificationID`, `userID`, `message`, `timestamp`
- **Feedback:** Attributes: `feedbackID`, `rating`, `comments`

<img src="new uml.png">
- Figure 1: UML


### Use Case 1: Request Ride

- **Use Case Name:** Request Ride
- **Scope:** Riksha Ride-Sharing Application
- **Level:** User Goal
- **Primary Actor:** Passenger
- **Supporting Actor:** Driver
- **Stakeholders and Interests:**
  - **Passenger:** Wants to quickly and conveniently book a ride.
  - **Driver:** Wants to receive ride requests to earn income.
  - **Riksha Administration:** Aims to facilitate seamless ride bookings and maximize utilization.
- **Preconditions:**
  - The passenger is logged into the app and has a valid payment method on file.
- **Success Guarantee:**
  - The ride is successfully requested, and a driver is assigned.
- **Main Success Scenario:**
  1. The passenger opens the app and enters the destination.
  2. The system calculates the estimated fare and displays it to the passenger.
  3. The passenger confirms the request.
  4. The system searches for available drivers nearby.
  5. A driver accepts the request.
  6. The system notifies the passenger of the assigned driver’s details.
- **Extensions:**
  - **4a.** No drivers are available:
    - The system notifies the passenger that no drivers are currently available and suggests trying again later.
- **Special Requirements:**
  - The system must provide real-time availability of drivers.
  - The estimated fare should account for current traffic conditions and dynamic pricing.
- **Postconditions:**
  - The ride request is recorded in the system.
  - The passenger and driver are connected via the app.

### Use Case 2: Accept Ride

- **Use Case Name:** Accept Ride
- **Scope:** Riksha Ride-Sharing Application
- **Level:** User Goal
- **Primary Actor:** Driver
- **Supporting Actor:** Passenger
- **Stakeholders and Interests:**
  - **Driver:** Wants to accept ride requests to earn income.
  - **Passenger:** Wants a quick response from a nearby driver.
  - **Riksha Administration:** Aims to ensure efficient matching between drivers and passengers.
- **Preconditions:**
  - A ride request has been made by a passenger.
  - The driver is online and available for new ride requests.
- **Success Guarantee:**
  - The driver successfully accepts the ride, and the passenger is notified.
- **Main Success Scenario:**
  1. The driver receives a ride request notification on the app.
  2. The system displays the passenger’s pickup location and ride details.
  3. The driver reviews the details and accepts the ride.
  4. The system notifies the passenger that a driver has accepted the ride.
- **Extensions:**
  - **3a.** Driver rejects the ride:
    - The system searches for another available driver.
  - **3b.** Driver is unavailable after accepting:
    - The system reassigns the ride to a different driver and notifies the passenger.
- **Special Requirements:**
  - The system must notify the driver within a few seconds of a ride request.
  - The driver’s app must show accurate location and ride details.
- **Postconditions:**
  - The driver’s acceptance is logged in the system.
  - The ride status is updated to “Driver En Route.”

### Use Case 3: Start the Ride

- **Use Case Name:** Start the Ride
- **Scope:** Riksha Ride-Sharing Application
- **Level:** User Goal
- **Primary Actor:** Driver
- **Supporting Actor:** Passenger
- **Stakeholders and Interests:**
  - **Driver:** Wants to start the ride to complete the service and earn income.
  - **Passenger:** Wants to ensure the ride begins smoothly and on time.
  - **Riksha Administration:** Monitors ride initiation for service quality and compliance.
- **Preconditions:**
  - The driver has arrived at the passenger's pickup location.
  - The passenger is in the vehicle, and both have verified each other's details.
- **Success Guarantee:**
  - The ride starts successfully, and the system begins tracking the trip.
- **Main Success Scenario:**
  1. The driver arrives at the pickup location and the passenger enters the vehicle.
  2. The driver confirms the passenger’s identity via the app.
  3. The passenger confirms the driver’s details.
  4. The driver taps “Start Ride” in the app.
  5. The system begins real-time tracking of the ride.
- **Extensions:**
  - **2a.** Passenger fails to verify identity:
    - The driver contacts Customer Support for verification assistance.
- **Special Requirements:**
  - The system must accurately track the ride in real time and provide estimated arrival times.
  - Both driver and passenger should have access to a panic button in case of emergencies.
- **Postconditions:**
  - The ride status is updated to “In Progress.”
  - The system begins fare calculation based on distance and time.

### Use Case 4: Rate The Ride

- **Use Case Name:** Rate The Ride
- **Scope:** Riksha Ride-Sharing Application
- **Level:** User Goal
- **Primary Actor:** Passenger
- **Stakeholders and Interests:**
  - **Passenger:** Wants to provide feedback on the ride experience and rate the driver.
  - **Driver:** Interested in receiving feedback to improve their service.
  - **Riksha Administration:** Uses the ratings to monitor service quality and take action if necessary.
- **Preconditions:**
  - The ride has been completed, and the payment has been processed.
- **Success Guarantee:**
  - The passenger successfully submits a rating and feedback, and the driver is notified.
- **Main Success Scenario:**
  1. After the ride ends, the passenger receives a prompt to rate the ride.
  2. The passenger selects a rating and optionally provides feedback.
  3. The system records the rating and feedback.
  4. The driver is notified of the new rating.
  5. The rating is stored in the driver's profile for future reference.
- **Extensions:**
  - **2a.** Passenger skips the rating:
    - The system reminds the passenger to rate the ride later.
    - If the passenger still does not rate, the ride is marked as unrated.
- **Special Requirements:**
  - The system must ensure that the rating and feedback are securely stored and cannot be altered by the driver.
  - Anonymity must be preserved if the passenger chooses not to disclose their identity in feedback.
- **Postconditions:**
  - The ride is marked as completed and rated.
  - The driver’s rating is updated, and the feedback is logged.

### Use Case 5: Verify Driver Information

- **Use Case Name:** Verify Driver Info
- **Scope:** Riksha Ride-Sharing Application
- **Level:** User Goal
- **Primary Actor:** Passenger
- **Supporting Actor:** Driver
- **Stakeholders and Interests:**
  - **Passenger:** Wants to ensure the driver matches the profile and vehicle details provided.
  - **Driver:** Wants to assure passengers of their identity and legitimacy.
  - **Riksha Administration:** Wants to ensure that drivers are properly verified for safety and trust.
- **Preconditions:**
  - The passenger has requested a ride, and a driver has been assigned.
- **Success Guarantee:**
  - The passenger successfully verifies the driver's identity and vehicle information.
- **Main Success Scenario:**
  1. After a driver accepts the ride, the passenger receives the driver's details (name, photo, vehicle model, and license plate).
  2. The passenger reviews the driver's details before the ride begins.
  3. Upon the driver's arrival, the passenger checks the vehicle and driver against the provided details.
  4. The passenger confirms the driver's identity in the app.
  5. The system updates the ride status to “Verified.”
- **Extensions:**
  - **3a.** Driver's details do not match:
    - The passenger contacts Customer Support through the app.
    - Customer Support verifies the issue and either assigns a new driver or cancels the ride with a refund.
- **Special Requirements:**
  - The system must provide clear and accurate driver information.
  - Verification processes should be completed quickly to avoid delays in starting the ride.
- **Postconditions:**
  - The ride status is updated to “Verified” if the driver’s details match.
  - The ride may be canceled or reassigned if the verification fails.

### Use Case 6: Provide Customer Support

- **Use Case Name:** Provide Customer Support
- **Scope:** Riksha Ride-Sharing Application
- **Level:** User Goal
- **Primary Actor:** Passenger
- **Supporting Actor:** Driver, Customer Support
- **Stakeholders and Interests:**
  - **Passenger:** Wants to resolve issues or get assistance with their ride experience.
  - **Driver:** Wants to resolve any issues related to the ride.
  - **Customer Support:** Aims to assist passengers and drivers in resolving their issues efficiently.
- **Preconditions:**
  - Passenger or driver has encountered an issue that requires assistance.
- **Success Guarantee:**
  - The issue is resolved to the satisfaction of the passenger and/or driver.
- **Main Success Scenario:**
  1. The passenger or driver identifies an issue and opens the Customer Support section in the app.
  2. The system presents a list of common issues and FAQs.
  3. The user selects the issue that best describes their problem.
  4. The system attempts to resolve the issue with automated tools or FAQs.
  5. If the issue is unresolved, the system connects the user

<img src="Screenshot 2024-08-11 030553.png">
`Figure 2: Domain Model`

<img src="SSD1111.png">
`Figure 3: Request Ride`

<img src="SSD11111.png">
`Figure 4: Rate Ride`

<img src="SSD113.png">
`Figure 5: Start Ride`

<img src="SSD2.png">
`Figure 6: Verify Driver Info`

<img src="SSD555.png">
`Figure 7: Provide Customer Support`
