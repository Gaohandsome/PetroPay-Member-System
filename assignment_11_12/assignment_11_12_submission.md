Sprint Goal, Mini-ADR & Mini-API Description
1. Sprint Goal
Sprint Goal: Implement user profile basic information retrieval functionality.
2. Mini-ADR
• Decision: Use JWT for API authentication
• Reason: Stateless and scalable for distributed services
• Consequence: Reduced server session storage overhead
3. Mini-API Description
• Endpoint: GET /api/users/profile
• Request: Authorization header (Bearer JWT token)
• Success: 200 OK + { id, username, email, createdAt }
• Fail: 401 Unauthorized / 403 Forbidden
• Description: Retrieves authenticated user's basic profile data
