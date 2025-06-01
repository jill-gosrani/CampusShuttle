# CampusShuttleSystem

**Real-Time University Shuttle Simulator**  
_Last Updated: Wednesday, April 23, 2025_

---

## 🚌 Overview

This project simulates a real-time university shuttle system with dynamic routing and ETA calculations.

**Key Assumptions**:

- Single active shuttle traveling at **18 mph** (configurable via API).
- Maximum capacity: **30 students** (configurable via API).
- Departure logic: Waits for _min(15 minutes, time to fill shuttle)_.
- No predefined route – shuttle drops students at their addresses.
- Daily operational schedule.
- **ETA Calculations**:
  - _Inside shuttle_: Sum of previous drop ETAs + travel time from last student's address.
  - _Outside shuttle_: Time to complete current drops + return to stop.
- Distance calculations use [Haversine formula](https://en.wikipedia.org/wiki/Haversine_formula) for Earth's curvature.
- Location interpolation via arithmetic method (non-geodesic).

---

## ⚙️ Implementation

**Tech Stack**:

- Backend: Java Spring Boot
- Database: MySQL
- Best practices followed for scalability (though not optimized for production deployment).

---

## 🛠️ Setup

1. **Clone Repository**:  
   git clone https://github.com/jill-gosrani/CampusShuttle.git:
2. **Install MySQL**:  
   Download from [MySQL Official Site](https://dev.mysql.com/downloads/).
3. **Configure Database**:  
   CREATE DATABASE shuttle_db;
   -- Ensure root user has privileges
4. **Update Credentials**:  
   Modify `src/main/resources/application.properties`:  
   spring.datasource.username = your_username
   spring.datasource.password = your_password
5. **Build & Run**:

- Install Maven dependencies in IntelliJ.
- Execute `Cis687Application.java`.

---

## 👨💻 Project Lead

[Jill Gosrani](https://jill-gosrani.github.io/)

---

_Optimized for clarity and maintainability – contributions welcome!_
