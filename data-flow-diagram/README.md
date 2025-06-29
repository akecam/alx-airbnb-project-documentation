## Data Flow Diagram

# Key Components:

1. External Entities:
   * `Guest`: Initiates searches, bookings, reviews
   * `Host`: Manages listings and bookings
   * `Admin`: Oversees system operations
   * `Payment Gateway`: Handles transactions
   * `OAuth Provider`: Authenticates users

2. Processes:
   * *User Management*: Handles registration/login (OAuth integrated)
   * *Listing Management*: CRUD operations for properties
   * *Search Engine*: Processes filters/pagination
   * *Booking Manager*: Coordinates reservations/cancellations
   * *Payment Processor*: Manages transactions & payouts
   * *Review System*: Handles ratings/responses
   * *Notification Service*: Triggers email/app alerts
   * *Admin Dashboard*: Central control panel

3. Data Stores:
   * User Database: Profiles/credentials
   * Listings Database: Property details/availability
   * Bookings Database: Reservations/statuses
   * Payments Database: Transactions/records
   * Reviews Database: Ratings/responses
  
4. Critical Data FLow:

![Critical_data_flow](https://github.com/user-attachments/assets/7b891f61-e99d-49f7-ae8a-c7036acf0200)


# Data FLow Diagram

![data-flow](https://github.com/user-attachments/assets/92a025bf-a20c-451b-94c3-eddc64516ab2)

# Flow Explanation:

1. User Journey:
   * Guest submits search → Search Engine queries Listings DB → Results returned
   * Booking request → Booking Manager creates record → Payment Processor charges → Confirmation sent

2. Host Operations:
   * New listing → Stored in Listings DB → Becomes searchable
   * Booking cancellation → Updates Bookings DB → Triggers refund via Payment Processor

3. Payment Flow:
   * Booking confirmation → Payment request to Gateway → Transaction recorded → Payout scheduled to Host

4. Admin Oversight:
   * Dashboard pulls data from all databases → Generates reports → Allows manual overrides

5. Notifications:
   * Triggered by booking/payment/review events → Sent to relevant users via email/app

6. Data Integrity:
   * All processes read/write to centralized databases
   * Admin Dashboard maintains data consistency


