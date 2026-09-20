# FitFlow Redesign

## IT3060 – Human Computer Interaction
### BSc (Hons) in Information Technology – Year 3 Semester 2, 2026
### Lab Exercise 05

FitFlow Redesign is a technology architecture and redesign project for
a fitness tracking application. The project focuses on selecting an
appropriate technology stack to support cross-platform development,
AI-powered personalized workouts, nutrition tracking, social features,
real-time communication, security, and scalability.

---

## Project Overview

FitFlow is a fitness tracking application redesigned to improve user
engagement and provide a more personalized fitness experience.

The redesigned system includes:

- AI-powered personalized workout plans
- Nutrition tracking and recommendations
- Social sharing and community features
- Real-time notifications and updates
- Fitness progress tracking
- Cross-platform Android, iOS, and web support
- Secure user authentication and authorization
- Scalable backend services

---

## Selected Technology Stack

| Layer | Technology |
|---|---|
| Frontend | Flutter + Dart |
| Main Backend | NestJS + TypeScript |
| AI Service | Python + FastAPI |
| Database | PostgreSQL |
| Cache | Redis |
| Authentication | Auth0 |
| Real-Time Communication | WebSockets / Socket.IO |
| File Storage | Object Storage |
| Deployment | Docker + Cloud Hosting |
| Source Control | GitHub |

---

## Why This Stack?

### Flutter
Flutter provides a shared codebase for Android, iOS, and web while
supporting high-performance and interactive user interfaces.

### NestJS + TypeScript
NestJS provides a modular and maintainable backend architecture suitable
for REST APIs, business logic, validation, and real-time functionality.

### Python + FastAPI
FastAPI is used as a separate AI microservice because Python provides
a strong ecosystem for machine learning and AI development.

### PostgreSQL
PostgreSQL provides reliable relational storage for user profiles,
workout plans, nutrition records, social data, and other structured
information.

### Redis
Redis provides caching for frequently accessed and temporary data,
helping improve application performance.

### Auth0
Auth0 provides managed authentication, identity management, access
tokens, and authorization integration.

### WebSockets / Socket.IO
WebSockets and Socket.IO support real-time social updates and
notifications.

---

## Project Structure

```text
fitflow-redesign/
│
├── frontend/
│   └── README.md
│
├── backend/
│   └── README.md
│
├── ai-service/
│   └── README.md
│
├── docs/
│   ├── README.md
│   ├── technology-comparison.md
│   ├── decision-matrix.md
│   ├── architecture.md
│   ├── architecture-diagram.jpeg
│   └── ADR.md
│
├── .gitignore
└── README.md
