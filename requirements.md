# Backend Feature Specifications

## Feature 1: User Authentication
*Secure account access with OAuth/email-password options*

### Functional Requirements
1. **Registration**:
   - Email/password signup with verification
   - OAuth integration (Google/Facebook)
   - Profile initialization (role: guest/host)
2. **Login**:
   - JWT token generation (access + refresh)
   - Rate limiting (5 attempts/min)
   - Session management
3. **Security**:
   - Password hashing (bcrypt)
   - OAuth token validation
   - Refresh token rotation

### Technical Specifications
**API Endpoints**:
| Method | Path               | Description                |
|--------|--------------------|----------------------------|
| POST   | `/auth/register`   | Email/password registration |
| POST   | `/auth/oauth`      | OAuth registration/login   |
| POST   | `/auth/login`      | Email/password login       |
| POST   | `/auth/refresh`    | Refresh access token       |
| POST   | `/auth/verify`     | Email verification         |

**Input/Output**:
```json
// REGISTER INPUT
{
  "email": "user@domain.com",
  "password": "SecurePass123!",
  "role": "host" // or "guest"
}

// SUCCESS OUTPUT
{
  "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "expires_in": 3600,
  "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
