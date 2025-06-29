## Use case Diagram

# Key Components Explained:

1. Actors:
   * `Guest`: Unregistered users or renters
   * `Host`: Property owners
   * `Admin`: System administrator
   * `Payment Gateway`: External payment system
   * `OAuth Provider`: External authentication service

2. User Management:
   * `User Registration`: For guests/hosts to create accounts
   * `Login/Authentication`: Supports email/password + OAuth (includes OAuth Provider)
   * `Manage Profile`: For hosts to update their information (guests can extend this)

3. Property Listings:
   * `Add Listing`: Hosts create new property entries
   * `Edit/Delete Listing`: Hosts modify existing listings
   * `Search Listings`: Available to all users (includes filtering and pagination)

4. Booking System:
   * `Create Booking`: Guests initiate reservations
   * `Cancel Booking`: Guests/hosts terminate bookings
   * `Track Booking Status`: Monitors booking states (Pending/Confirmed/Canceled/Completed)

5. Payments:
   * `Process Payment`: Secure transaction handling (includes Payment Gateway)
   * `Handle Payouts`: Automatic transfers to hosts (host-specific extension)

6. Reviews:
   * `Write Review`: Guests rate properties
   * `Respond to Review`: Hosts reply to feedback

7. Notifications:
   * Automatic `Send Notifications` for bookings/payments (triggered by relevant use cases)

8. Admin Dashboard:
   * Centralized management for users, listings, bookings, and payments

# Relationships:
  * `<<include>>`: Mandatory dependency (e.g., payment processing requires gateway)
  * `<<extend>>`: Optional functionality (e.g., profile management extends guest capabilities)

Arrows indicate actor-initiated use cases

![features_and_functionalities_1_](https://github.com/user-attachments/assets/10e19e0a-4967-467f-b8ee-35bffcf6f1a4)


