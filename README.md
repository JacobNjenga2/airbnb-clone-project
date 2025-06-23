# airbnb-clone-project


## Team Roles


## 📦 Technology Stack

| Technology                                                      | Purpose                                                                                                                                              |
| --------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Python**                                                      | Primary programming language used to build the backend logic.                                                                                        |
| **Django**                                                      | High-level Python web framework that simplifies building robust backend services and RESTful APIs.                                                   |
| **Django REST Framework (DRF)**                                 | A powerful toolkit for building Web APIs on top of Django, enabling serialization, authentication, and more.                                         |
| **PostgreSQL**                                                  | Relational database used to store and manage structured application data. Ideal for production-grade applications.                                   |
| **SQLite**                                                      | Lightweight default database used during local development and testing.                                                                              |
| **GraphQL** *(optional if used)*                                | An API query language that allows clients to request exactly the data they need—used when flexibility in querying is important.                      |
| **Docker**                                                      | Containerization platform used to package the app and its dependencies to ensure consistency across environments (development, testing, production). |
| **Git**                                                         | Version control system used to manage source code changes and collaborate with others.                                                               |
| **GitHub**                                                      | Cloud platform used to host and manage code repositories, issues, and pull requests.                                                                 |
| **Heroku / Render / Railway** *(choose based on what you used)* | Platform-as-a-Service (PaaS) used for deploying and hosting the web application online.                                                              |
| **Postman**                                                     | API testing tool used to test and document API endpoints.                                                                                            |
| **Jenkins / GitHub Actions** *(if used)*                        | CI/CD tool used to automate testing, building, and deployment of code.                                                                               |


## 🧩 Database Design
This project uses a relational database structure to manage data efficiently. Below are the core entities and their relationships:
#🔑 Key Entities & Fields
1. Users
Represents individuals who use the platform (hosts or guests).
**Fields:**
id: Unique identifier (Primary Key)
username: Unique login name
email: Contact email
password: Hashed password
role: Defines if the user is a host, guest, or admin
2. Properties
Represents the listings added by hosts.
Fields:
id: Unique property identifier
user_id: Foreign Key – references Users
title: Name of the property
location: Address or general area
price_per_night: Rental cost per night
3. Bookings
Represents reservation details made by users.
Fields:
id: Unique booking ID
user_id: Foreign Key – references Users (guest)
property_id: Foreign Key – references Properties
check_in: Start date of booking
check_out: End date of booking
4. Reviews
Captures feedback left by guests about properties.
Fields:
id: Unique review ID
user_id: Foreign Key – references Users (guest)
property_id: Foreign Key – references Properties
rating: Numeric score (e.g., 1-5)
comment: Text feedback
5. Payments
Tracks completed transactions.
Fields:
id: Unique payment ID
booking_id: Foreign Key – references Bookings
amount: Total cost charged
payment_status: e.g., pending, completed, failed
payment_date: Timestamp of transaction
# 🔗 Entity Relationships
A User can have many Properties (if they are a host).
A Property belongs to one User.
A User can make many Bookings (if they are a guest).
A Booking is associated with one Property and one User.

A Property can have many Reviews from different Users.
A Booking can have one Payment.

## ✨ Feature Breakdown

The Airbnb Clone project includes several core features that replicate the core functionalities of a short-term rental platform. Each feature is designed to provide a seamless experience for users, whether they are guests or hosts.

---

### 👥 User Management
Users can sign up, log in, and manage their profiles. The system supports role-based access control, distinguishing between guests, hosts, and administrators.

---

### 🏡 Property Management
Hosts can list properties by providing essential information such as title, description, price, and location. They can also edit or delete listings and manage availability.

---

### 📅 Booking System
Guests can view property listings, select available dates, and make bookings. The system ensures that double bookings are avoided and booking history is recorded.

---

### 💳 Payment Integration
Secure payment processing is integrated for booking confirmation. Users can view payment status, and transactions are stored with booking details for future reference.

---

### ⭐ Reviews and Ratings
After their stay, guests can leave reviews and ratings for properties. This builds trust within the platform and helps future users make informed decisions.

---

### 🔎 Search and Filtering
Users can search for properties using filters like location, price range, property type, and availability. This enhances discoverability and improves the user experience.

---

### 🛠️ Admin Panel
Administrators have access to a dedicated dashboard to manage users, properties, bookings, and reported content. This ensures platform integrity and smooth operations.

---


