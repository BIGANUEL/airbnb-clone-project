# 🏡 Airbnb Clone - Backend

## 🚀 Project Overview

This is a backend implementation of an **Airbnb Clone** project. The system is designed to manage user interactions, property listings, bookings, payments, and reviews. It aims to provide a seamless and secure experience for both users and hosts.

### 🎯 Project Goals

- Enable secure user authentication and management.
- Allow hosts to list and manage their rental properties.
- Provide a booking system to reserve properties.
- Integrate secure and reliable payment processing.
- Enable users to leave reviews and rate properties.
- Ensure high performance with caching and optimized queries.

---

## 👥 Team Roles

### Backend Developer
Responsible for creating API endpoints, handling business logic, and integrating all backend services.

### Database Administrator
Designs the database schema, ensures data integrity, and implements optimizations like indexing.

### DevOps Engineer
Handles deployment, Docker setup, CI/CD pipelines, and cloud infrastructure for scaling and monitoring.

### QA Engineer
Performs testing of all backend functionalities, ensuring everything works as expected and is bug-free.

---

## ⚙️ Technology Stack

| Technology     | Purpose                                                                 |
|----------------|-------------------------------------------------------------------------|
| **Django**     | Web framework used to build the backend and RESTful APIs.              |
| **Django REST Framework** | Toolkit to build flexible, powerful REST APIs.                     |
| **GraphQL**    | Provides an efficient, flexible query language for API interaction.     |
| **PostgreSQL** | Relational database system used for storing all project data.           |
| **Redis**      | In-memory data store for caching and session management.                |
| **Celery**     | Handles asynchronous tasks like notifications and payment processing.   |
| **Docker**     | Containerizes the application for consistent development and deployment.|
| **GitHub Actions** | Automates testing and deployment in CI/CD pipelines.                    |

---

## 🧩 Database Design

### 🧑 Users
- `id`: Unique identifier  
- `username`: User’s name  
- `email`: Email address  
- `password`: Hashed password  
- `role`: User or Host  

### 🏠 Properties
- `id`: Property ID  
- `owner_id`: Linked to a user  
- `title`: Property name  
- `location`: Address or coordinates  
- `price_per_night`: Cost of staying per night  

### 📅 Bookings
- `id`: Booking ID  
- `user_id`: Linked to the guest  
- `property_id`: Linked to the booked property  
- `check_in`: Start date  
- `check_out`: End date  

### 💳 Payments
- `id`: Payment ID  
- `booking_id`: Linked to a booking  
- `amount`: Total cost  
- `status`: Paid, Pending, Failed  
- `transaction_date`: Timestamp  

### ⭐ Reviews
- `id`: Review ID  
- `user_id`: Author of the review  
- `property_id`: Reviewed property  
- `rating`: 1–5 stars  
- `comment`: Feedback  

### 🔗 Relationships
- A **User** can create many **Properties**.  
- A **User** can make many **Bookings**.  
- Each **Booking** is tied to one **Property** and one **User**.  
- Each **Payment** is tied to one **Booking**.  
- Each **Review** is tied to one **Property** and one **User**.

---

## 🛠️ Feature Breakdown

### User Management
Users can register, log in, and update their profile. Authentication ensures only verified users can access certain features.

### Property Management
Hosts can create, update, and delete property listings. Each listing includes details like title, description, price, and location.

### Booking System
Users can search and book available properties. The system tracks booking dates, prevents conflicts, and stores booking history.

### Payment Processing
Secure payment endpoints handle transactions tied to bookings. All payments are recorded and status-tracked.

### Review System
After completing a stay, users can review properties. Reviews include star ratings and comments, helping future guests make decisions.

---

## 🔐 API Security

### Authentication
Only registered users can access protected endpoints using tokens (e.g., JWT).

### Authorization
Different permissions for users and hosts (e.g., only the host can update their property).

### Rate Limiting
Prevents abuse by limiting the number of requests a user can make in a given time.

### Importance of Security
- **User Data**: Prevent unauthorized access to personal information.  
- **Payments**: Secure financial data to avoid fraud or data leaks.  
- **Integrity**: Ensure no user can manipulate data that doesn’t belong to them.

---

## ⚙️ CI/CD Pipeline

### What is CI/CD?
CI/CD stands for Continuous Integration and Continuous Deployment. It ensures that new code is tested and deployed automatically without breaking the application.

### Tools Used
- **GitHub Actions**: Automatically runs tests and deploys the app when code is pushed.
- **Docker**: Ensures consistency across all development and production environments.

### Benefits
- Faster and safer releases  
- Early bug detection  
- Streamlined development workflow  

---

## 📦 Running Locally

```bash
# Clone the repo
git clone https://github.com/<your-username>/airbnb-clone-project.git
cd airbnb-clone-project

# Build and start the project
docker-compose up --build
