# FitFlow High-Level System Architecture

## IT3060 – Human Computer Interaction
### Lab Exercise 05 – FitFlow Redesign

## 1. Architecture Overview

The FitFlow redesign uses a hybrid and service-oriented architecture
designed to support Android, iOS, and web platforms while providing
AI-powered recommendations, real-time social features, nutrition
tracking, secure authentication, and scalable data management.

The main technologies used in the architecture are:

- Flutter – Cross-platform frontend
- NestJS + TypeScript – Main backend
- Python + FastAPI – AI microservice
- PostgreSQL – Primary relational database
- Redis – Caching and temporary data
- Auth0 – Authentication and authorization
- WebSockets / Socket.IO – Real-time communication
- Object Storage – Images and uploaded files
- Docker + Cloud Hosting – Deployment and scalability

---

# 2. Main Architecture Components

| Component | Responsibility |
|---|---|
| Flutter Frontend | Provides the user interface for Android, iOS, and web |
| NestJS Backend | Handles business logic, API endpoints, validation, and service coordination |
| Auth0 | Handles login, identity management, access tokens, and authorization integration |
| User Service | Manages profiles, preferences, and user settings |
| Workout Service | Manages exercises, workout plans, progress tracking, and fitness history |
| Nutrition Service | Manages meals, calories, nutrients, and nutrition tracking |
| Social Service | Manages posts, likes, comments, and social sharing |
| Notification Service | Handles workout reminders, social notifications, and system messages |
| AI Microservice | Generates personalized workout and nutrition recommendations |
| PostgreSQL | Main structured data store |
| Redis | Provides caching and temporary data storage |
| WebSocket Gateway | Provides real-time social updates and notifications |
| Object Storage | Stores user-uploaded images and other files |

---

# 3. High-Level Architecture Diagram

The following architecture diagram illustrates the interaction between
the FitFlow frontend, backend services, AI microservice, database,
cache, authentication service, real-time communication layer, and
object storage.

![FitFlow High-Level Architecture](architecture-diagram.png)

---

# 4. Data Flow – Personalized Workout Plans

The personalized workout plan feature uses the AI microservice to
generate recommendations based on user fitness information.

### Flow

1. The user enters fitness goals and preferences using the Flutter application.
2. The Flutter frontend sends the request to the NestJS backend.
3. The NestJS backend retrieves the required user profile and fitness history from PostgreSQL.
4. Relevant validated information is sent to the Python/FastAPI AI microservice.
5. The AI service processes the information and generates a personalized workout recommendation.
6. The generated workout plan is returned to the NestJS backend.
7. The workout plan is stored in PostgreSQL.
8. The NestJS backend returns the personalized plan to the Flutter application.
9. The Flutter application displays the workout recommendation to the user.

---

# 5. Data Flow – Social Sharing

The social sharing feature allows users to share fitness activities
and provides real-time updates to connected users.

### Flow

1. The user completes a workout.
2. The Flutter application sends the social sharing request to the NestJS Social API.
3. The backend validates the request and user permissions.
4. The social post is stored in PostgreSQL.
5. A real-time event is published.
6. The WebSocket Gateway distributes the update to connected followers.
7. The Notification Service generates relevant notifications.
8. Followers receive the social update or notification.

---

# 6. Data Flow – Nutrition Tracking

The nutrition tracking feature stores meal information and can use the
AI service to generate nutrition recommendations.

### Flow

1. The user enters meal details using the Flutter frontend.
2. The information is sent to the NestJS Nutrition API.
3. The backend validates the nutrition information.
4. The meal record is stored in PostgreSQL.
5. The application calculates the user's daily nutrition summary.
6. Frequently accessed information can be stored in Redis.
7. Relevant information can be sent to the FastAPI AI service.
8. The AI service generates nutrition recommendations.
9. The nutrition summary and recommendations are returned to the Flutter dashboard.

---

# 7. Security Considerations

The FitFlow architecture should implement the following security
measures:

- All communication should use HTTPS/TLS.
- Authentication should be managed using Auth0 and validated access tokens.
- Role-based authorization should be applied to protected backend operations.
- Sensitive information should be encrypted in transit and at rest.
- Input validation should be implemented in NestJS and FastAPI.
- Database credentials and API keys should be stored in environment variables or a secrets manager.
- Rate limiting should protect public and sensitive endpoints.
- Audit logs should record important access and administrative actions.
- User privacy and consent should be considered when collecting fitness and health-related data.
- Security testing should be performed before production deployment.

---

# 8. Scalability Considerations

The following approaches can improve the scalability of FitFlow:

- Deploy backend services using containers.
- Use horizontal scaling for the NestJS API.
- Use Redis to reduce repeated database queries.
- Add database indexes for frequently queried fields.
- Use pagination for workout history, social posts, and nutrition records.
- Separate AI workloads from the main backend API.
- Use asynchronous queues for long-running AI tasks.
- Store images in object storage rather than the primary database.
- Use monitoring and logging to identify performance issues.

---

# 9. Integration Considerations

The architecture separates the main application logic from AI-specific
processing.

NestJS coordinates the main FitFlow services, while FastAPI handles
AI/ML workloads. PostgreSQL provides structured persistent storage,
while Redis improves access to frequently requested data.

Auth0 is integrated with the backend for identity and access control,
and WebSockets / Socket.IO provide real-time communication for social
features and notifications.

This separation makes it possible to maintain and scale individual
parts of the FitFlow system according to application demand.

---

# 10. Architecture Summary

The proposed FitFlow architecture combines a cross-platform Flutter
frontend with a modular NestJS backend and a separate Python/FastAPI
AI microservice.

PostgreSQL provides reliable structured data storage, Redis improves
performance through caching, Auth0 provides managed authentication,
and WebSockets / Socket.IO support real-time communication.

The architecture is designed to support FitFlow's personalized
workouts, social sharing, nutrition tracking, security requirements,
and future scalability.
