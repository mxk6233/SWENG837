<p align="center">
    <img src="Screenshot 2024-08-10 055333.png" alt="Car Ride Share System" Height="150",Width="750">
    <br />
</p>
<h2 align="center">Real-time Ride-Sharing Service</h2>

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

Here are six use case scenarios for the "Riksha" ride-sharing service, along with the identified actors:

### 1. **Use Case: Register as a Passenger**
   - **Scenario:** A user wants to register as a passenger on the Riksha platform.
   - **Actors:**
     - **Primary Actor:** User (Passenger)
     - **Supporting Actor:** System (Riksha Platform)
   - **Description:**
     - The user opens the Riksha mobile app and selects the option to register as a passenger.
     - The system prompts the user to enter their personal details (name, email, phone number) and create a password.
     - The user submits the form, and the system verifies the information.
     - The system creates a new passenger profile and sends a confirmation message to the user.

### 2. **Use Case: Request a Ride**
   - **Scenario:** A registered passenger wants to request a ride.
   - **Actors:**
     - **Primary Actor:** Passenger
     - **Supporting Actor:** System (Riksha Platform)
     - **Secondary Actor:** Driver
   - **Description:**
     - The passenger logs into the Riksha app and enters their current location and desired destination.
     - The system calculates the estimated fare and displays it to the passenger.
     - The passenger confirms the request, and the system searches for available drivers nearby.
     - The system matches the passenger with a driver and notifies both parties.
     - The driver accepts the ride, and the system provides the driver's details to the passenger.

### 3. **Use Case: Accept a Ride Request**
   - **Scenario:** A driver receives a ride request and decides whether to accept it.
   - **Actors:**
     - **Primary Actor:** Driver
     - **Supporting Actor:** System (Riksha Platform)
     - **Secondary Actor:** Passenger
   - **Description:**
     - The driver receives a notification on their Riksha app about a new ride request.
     - The system displays the passenger's pick-up location, destination, and estimated fare.
     - The driver reviews the details and decides to accept the ride.
     - The system confirms the acceptance and notifies the passenger.
     - The driver navigates to the passenger's pick-up location using the app's GPS.

### 4. **Use Case: Complete a Ride**
   - **Scenario:** A driver completes a ride and marks it as finished.
   - **Actors:**
     - **Primary Actor:** Driver
     - **Supporting Actor:** System (Riksha Platform)
     - **Secondary Actor:** Passenger
   - **Description:**
     - After reaching the passenger's destination, the driver marks the ride as completed in the Riksha app.
     - The system calculates the final fare, taking into account any dynamic pricing adjustments.
     - The system processes the payment using the passenger's preferred payment method.
     - Both the driver and the passenger receive a summary of the ride details, including the fare.
     - The system prompts both the driver and the passenger to rate each other.

### 5. **Use Case: Process Payment**
   - **Scenario:** A passenger's payment is processed after the ride is completed.
   - **Actors:**
     - **Primary Actor:** System (Riksha Platform)
     - **Secondary Actor:** Passenger
     - **Supporting Actor:** Payment Gateway
   - **Description:**
     - Once the ride is completed, the system calculates the final fare.
     - The system checks the passenger's stored payment method (e.g., credit card, digital wallet).
     - The system initiates a payment request through the integrated payment gateway.
     - The payment gateway processes the transaction and returns a confirmation to the system.
     - The system updates the passenger's ride history and sends a receipt via email or SMS.

### 6. **Use Case: Provide Feedback**
   - **Scenario:** A passenger provides feedback on a completed ride.
   - **Actors:**
     - **Primary Actor:** Passenger
     - **Supporting Actor:** System (Riksha Platform)
     - **Secondary Actor:** Driver
   - **Description:**
     - After completing a ride, the passenger is prompted to provide feedback.
     - The passenger rates the ride on a scale of 1 to 5 stars and can leave additional comments.
     - The system records the feedback and associates it with the driver's profile.
     - The system uses the feedback to update the driver's overall rating.
     - The passenger can view their feedback history within the app.



