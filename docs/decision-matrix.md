# FitFlow Weighted Technology Decision Matrix

## IT3060 – Human Computer Interaction
### Lab Exercise 05 – FitFlow Redesign

This document presents the weighted technology decision matrices used
to evaluate the frontend, backend, database, and authentication options
for the FitFlow redesign.

Each technology is scored using a scale from 1 to 5:

- 1 = Very Poor
- 2 = Poor
- 3 = Average
- 4 = Good
- 5 = Excellent

The weights reflect the importance of performance, scalability,
development speed, security, cost, AI/ML integration, maintainability,
and other FitFlow-specific requirements.

---

# 1. Frontend Decision Matrix

The frontend technologies evaluated are Flutter, React Native,
Kotlin Multiplatform, and Swift/SwiftUI.

| Criteria | Weight | Flutter | React Native | Kotlin Multiplatform | Swift/SwiftUI |
|---|---:|---:|---:|---:|---:|
| Performance | 20% | 5 | 4 | 5 | 5 |
| Development Speed | 15% | 4 | 5 | 3 | 4 |
| Code Reusability | 20% | 5 | 4 | 4 | 2 |
| Web Compatibility | 15% | 4 | 4 | 3 | 1 |
| Ecosystem Support | 10% | 4 | 5 | 3 | 4 |
| AI/ML Integration | 5% | 4 | 4 | 4 | 5 |
| Maintenance Cost | 10% | 4 | 4 | 3 | 2 |
| Learning Curve | 5% | 4 | 4 | 3 | 4 |
| **Weighted Total** | **100%** | **4.40** | **4.30** | **3.65** | **3.20** |

## Result

Flutter receives the highest weighted score of **4.40** and is
recommended as the primary frontend framework for FitFlow.

Flutter provides a strong balance of performance, development speed,
code reusability, web compatibility, and maintainability. Its shared
codebase is particularly useful for FitFlow because the application
needs to support Android, iOS, and web platforms.

---

# 2. Backend Decision Matrix

The backend technologies evaluated are NestJS, FastAPI, and Go.

| Criteria | Weight | NestJS | FastAPI | Go |
|---|---:|---:|---:|---:|
| Performance | 20% | 4 | 4 | 5 |
| Development Speed | 15% | 4 | 5 | 3 |
| Scalability | 15% | 4 | 4 | 5 |
| AI/ML Integration | 15% | 3 | 5 | 3 |
| Real-Time Support | 10% | 5 | 4 | 4 |
| Security and Maintainability | 15% | 5 | 4 | 4 |
| Cost Efficiency | 10% | 4 | 4 | 5 |
| **Weighted Total** | **100%** | **4.05** | **4.35** | **4.00** |

## Result

FastAPI receives the highest overall weighted score of **4.35**,
mainly because of its strong AI/ML integration.

However, **NestJS is selected as the main FitFlow backend** because it
provides a structured and modular TypeScript architecture suitable for
the core application and a mid-sized development team.

**FastAPI is selected as a separate AI microservice** to handle
AI/ML workloads such as personalized workout plans and nutrition
recommendations.

This results in a hybrid backend architecture.

---

# 3. Database Decision Matrix

The database technologies evaluated are PostgreSQL, MongoDB,
Firebase, and DynamoDB.

| Criteria | Weight | PostgreSQL | MongoDB | Firebase | DynamoDB |
|---|---:|---:|---:|---:|---:|
| Query Performance | 15% | 5 | 4 | 3 | 5 |
| Scalability | 15% | 4 | 5 | 5 | 5 |
| Data Consistency | 20% | 5 | 4 | 3 | 4 |
| Health Data Structure | 15% | 5 | 4 | 3 | 3 |
| Real-Time Capabilities | 10% | 3 | 4 | 5 | 4 |
| AI/ML Integration | 10% | 5 | 5 | 4 | 4 |
| Cost Efficiency | 5% | 4 | 4 | 4 | 4 |
| Maintainability | 10% | 5 | 4 | 4 | 3 |
| **Weighted Total** | **100%** | **4.55** | **4.25** | **3.65** | **4.00** |

## Result

PostgreSQL receives the highest weighted score of **4.55** and is
selected as the primary database for FitFlow.

PostgreSQL provides reliable relational data management, transactions,
data consistency, structured health-data handling, and strong query
capabilities.

---

# 4. Authentication Decision Matrix

The authentication technologies evaluated are Firebase Authentication,
AWS Cognito, Auth0, and Supabase Authentication.

| Criteria | Weight | Firebase Auth | AWS Cognito | Auth0 | Supabase Auth |
|---|---:|---:|---:|---:|---:|
| Security Features | 25% | 4 | 5 | 5 | 4 |
| Development Speed | 15% | 5 | 3 | 4 | 5 |
| Authorization Flexibility | 15% | 4 | 5 | 5 | 4 |
| Real-Time Integration | 10% | 5 | 3 | 3 | 5 |
| Cost | 10% | 4 | 4 | 3 | 4 |
| Maintainability | 15% | 5 | 4 | 5 | 4 |
| AI/ML Integration | 5% | 4 | 4 | 4 | 4 |
| Health Data Compliance Readiness | 5% | 4 | 5 | 5 | 4 |
| **Weighted Total** | **100%** | **4.35** | **4.20** | **4.30** | **4.25** |

## Result

Firebase Authentication receives the highest illustrative weighted
score of **4.35**.

However, **Auth0 is selected for the proposed FitFlow architecture**
because of its identity management and authorization capabilities.

The final authentication choice may also depend on the development
team's budget, cloud infrastructure, and compliance requirements.

---

# 5. Overall Recommended Technology Stack

Based on the technology comparisons and decision matrices, the
following technology stack is proposed for the FitFlow redesign.

| Layer | Recommended Technology | Reason |
|---|---|---|
| Frontend | Flutter | Shared Android, iOS, and web interface |
| Main Backend | NestJS + TypeScript | Modular and maintainable APIs |
| AI Service | Python + FastAPI | Strong AI/ML ecosystem |
| Database | PostgreSQL | Reliable relational data and transactions |
| Cache | Redis | Fast caching and temporary data |
| Authentication | Auth0 | Managed identity and authorization integration |
| Real-Time Communication | WebSockets / Socket.IO | Social sharing and live updates |
| Deployment | Docker + Cloud Hosting | Consistent deployment and scalability |
| Source Control | GitHub | Collaboration and version control |

---

# 6. Overall Decision

The recommended FitFlow architecture uses a hybrid technology stack.

Flutter is used as the shared frontend for Android, iOS, and web.
NestJS with TypeScript manages the core application APIs and business
logic, while Python with FastAPI handles AI/ML workloads.

PostgreSQL provides reliable structured data storage, Redis improves
performance through caching, and Auth0 manages authentication and
authorization.

This architecture balances performance, development speed,
scalability, security, AI integration, and long-term maintainability
for the FitFlow redesign.
