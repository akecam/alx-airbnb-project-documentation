# Technical Specifications

## 1. User Authentication
- **Endpoints**:
  - POST /api/auth/register (201 Created)
  - POST /api/auth/login (200 OK)
- **Validation**:
  - Email regex: ^\S+@\S+\.\S+$
  - Password: 8+ chars with mixed case
- **Performance**: <500ms response @ 1000 RPS

## 2. Property Management
- **Endpoints**:
  - POST /api/properties (JWT required)
  - GET /api/properties?location=Paris&maxPrice=200
- **Data Model**:
  ```json
  {
    "title": "Paris Loft",
    "amenities": ["wifi", "kitchen"],
    "pricePerNight": 150
  }
