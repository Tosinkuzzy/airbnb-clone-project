Project Overview

The Airbnb Clone Project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. 
It involves a deep dive into full-stack development, focusing on backend systems, database design, API development, and application security. 
This project enables learners to understand complex architectures, workflows, and collaborative team dynamics while building a scalable web application.

Team Roles

Backend Developer: Responsible for implementing API endpoints, database schemas, and business logic.
Database Administrator: Manages database design, indexing, and optimizations.
DevOps Engineer: Handles deployment, monitoring, and scaling of the backend services.
QA Engineer: Ensures the backend functionalities are thoroughly tested and meet quality standards.

Technology Stack

Django: A high-level Python web framework used for building the RESTful API.
Django REST Framework: Provides tools for creating and managing RESTful APIs.
PostgreSQL: A powerful relational database used for data storage.
GraphQL: Allows for flexible and efficient querying of data.
Celery: For handling asynchronous tasks such as sending notifications or processing payments.
Redis: Used for caching and session management.
Docker: Containerization tool for consistent development and deployment environments.
CI/CD Pipelines: Automated pipelines for testing and deploying code changes.

Database Design

This project uses a relational database to manage users, properties, bookings, reviews, and payments. The structure is designed to ensure data integrity, easy querying, and scalability.

Entities & Key Fields
1. Users
user_id (Primary Key)

name

email (unique)

password_hash

created_at

Relationships:

A user can list multiple properties.

A user can make multiple bookings.

A user can leave multiple reviews.

2. Properties
property_id (Primary Key)

owner_id (Foreign Key → Users.user_id)

title

description

location

price_per_night

Relationships:

A property belongs to one user (owner).

A property can have many bookings.

A property can have many reviews.

3. Bookings
booking_id (Primary Key)

property_id (Foreign Key → Properties.property_id)

user_id (Foreign Key → Users.user_id)

check_in_date

check_out_date

status (e.g., confirmed, cancelled)

Relationships:

A booking belongs to a single property.

A booking is made by a single user.

A booking may have one associated payment.

4. Reviews
review_id (Primary Key)

property_id (Foreign Key → Properties.property_id)

user_id (Foreign Key → Users.user_id)

rating (1–5)

comment

created_at

Relationships:

A review belongs to a specific property.

A review is written by a single user.

5. Payments
payment_id (Primary Key)

booking_id (Foreign Key → Bookings.booking_id)

amount

payment_method

status (e.g., paid, pending)

payment_date

Relationships:

A payment is linked to one booking.

A payment confirms the booking’s financial transaction.

Entity Relationship Summary
Users ↔ Properties: One-to-Many (a user can own many properties).

Users ↔ Bookings: One-to-Many (a user can make many bookings).

Properties ↔ Bookings: One-to-Many (a property can be booked many times).

Properties ↔ Reviews: One-to-Many (a property can have many reviews).

Bookings ↔ Payments: One-to-One (each booking has one payment record).

Features Breakdown

1. User Authentication
Endpoints: /users/, /users/{user_id}/
Features: Register new users, authenticate, and manage user profiles.
3. Property Management
Endpoints: /properties/, /properties/{property_id}/
Features: Create, update, retrieve, and delete property listings.
4. Booking System
Endpoints: /bookings/, /bookings/{booking_id}/
Features: Make, update, and manage bookings, including check-in and check-out details.
5. Payment Processing
Endpoints: /payments/
Features: Handle payment transactions related to bookings.
6. Review System
Endpoints: /reviews/, /reviews/{review_id}/
Features: Post and manage reviews for properties.


