# Smart Parking Platform: Project Document
**Version:** 0.2
**Prepared by:** WE ARE $oftware ¢orp
**Date:** 09/09/2026

## Table of Contents
- [1. Research: Existing Software Landscape](#1-research-existing-software-landscape)
- [2. Vision and Scope](#2-vision-and-scope)
- [3. Software Requirements Specification](#3-software-requirements-specification-srs)
- [4. Project Planning](#4-project-planning)


## 1. Research: Existing Software Landscapes

Several parking solutions already exist in the market:

- **SpotHero** – Lets drivers pre-book parking spots at garages and lots in
  major cities. Strong on reservation/payment, weak on real-time availability
  (relies on operator-reported inventory, not live sensors).
- **ParkMobile** – Focuses on paying for on-street meter parking via phone.
  Good for street parking, does not address garage navigation or reservations.
- **ParkWhiz** – Similar to SpotHero; marketplace model for pre-booked parking,
  little to no live occupancy or in-garage navigation features.
- **Google Maps (parking layer)** – Shows general area difficulty ("limited
  parking") but no real per-spot availability, no reservation, no payment.

**How Smart Parking Platform differs:** unlike the above, our platform combines
*real-time* space-level availability, in-garage navigation, reservation, and
payment in one system, plus a dedicated operator dashboard for occupancy
analytics — something none of the above offer as a single integrated product.

## 2. Vision and Scope

### 2.1 Project Acquisition
This project was acquired by WE ARE $oftware ¢orp after being awarded a
contract through a competitive RFP process issued by a mid-sized city's
Department of Transportation, seeking to modernize parking availability
across its municipal parking garages.

### 2.2 About WE ARE $oftware ¢orp
WE ARE $oftware ¢orp is a fictitious software development studio specializing
in civic and mobility technology, with the resources to deliver full-stack
web, mobile, and backend solutions for municipal and commercial clients.

### 2.3 Project Overview
The Smart Parking Platform will allow drivers to locate, reserve, and pay for
parking in real time via web and mobile apps, while giving parking operators
a dashboard to monitor occupancy, pricing, and utilization.

### 2.4 Scope
**In scope:** user registration, real-time availability, map/navigation,
reservations, payments, operator dashboard, notifications.
**Out of scope (v1):** integration with autonomous vehicle systems, dynamic
city-wide traffic rerouting, hardware sensor manufacturing.

## 3. Software Requirements Specification (SRS)
Project: Smart Parking Platform
Version: 0.1
Date: [09/09/2026]

### 3.1 Introduction
**Purpose:** This document defines the requirements for the Smart Parking
Platform.
**Scope:** See Vision & Scope section above.

### 3.2 Overall Description
- **Users:** Drivers, parking operators, city administrators, finance staff
- **System Environment:** Web application + mobile app (iOS/Android)
- **Constraints:** Must comply with city data privacy ordinance; must
  integrate with third-party payment processors and mapping APIs
- **Assumptions:** Users have internet access; garages have sensors or
  reporting mechanisms for occupancy data

### 3.3 Functional Requirements 
- FR1: The system shall allow users to register and log in securely.
- FR2: The system shall display real-time parking availability on a map.
- FR3: The system shall allow users to reserve a parking space.
- FR4: The system shall process digital payments for reservations.
- FR5: The system shall generate a digital receipt after each transaction.

### 3.4 Non-Functional Requirements 
- NFR1: The system shall support at least 5,000 concurrent users.
- NFR2: Availability data shall refresh within 5 seconds.
- NFR3: The system shall maintain 99.9% uptime.

### 3.5 Use Cases (minimum 15, two fully written, rest as titles to expand)

**UC1 — Reserve a Parking Space**
- Actor: Driver
- Precondition: User is logged in
- Steps: 1) User searches for garage 2) Selects available spot 3) Confirms
  reservation 4) System processes payment 5) Confirmation sent
- Postcondition: Spot is held for user's arrival window

**UC2 — View Real-Time Occupancy (Operator)**
- Actor: Parking Operator
- Precondition: Operator is logged into admin dashboard
- Steps: 1) Operator opens dashboard 2) System displays live occupancy per
  level/zone 3) Operator filters by garage
- Postcondition: Operator has current occupancy snapshot

**Remaining use cases:**


3. Cancel a Reservation
4. Register a New Account
5. Navigate to Reserved Spot In-Garage
6. Pay via Saved Payment Method
7. Receive Low-Availability Notification
8. Set Dynamic Pricing (Operator)
9. Generate Occupancy Report (Operator)
10. Extend an Active Reservation
11. View Reservation History
12. Report a Parking Issue (e.g., occupied "reserved" spot)
13. Integrate with External Navigation App
14. Add a Vehicle to Profile
15. Process a Refund (Finance staff)


## 4. Project Planning

### 4.1 Work Breakdown Structure (WBS)

1. Authentication
   - 1.1 Login
     - Username/password login form
     - Login validation and error handling
   - 1.2 Registration
     - Account creation form
     - Email verification
   - 1.3 Session Management
     - Token/session handling
     - Auto-logout on inactivity

2. User / Operator Management
   - 2.1 Add User (Driver)
     - Driver account creation
     - Driver profile setup (vehicle info, payment method)
   - 2.2 Add Operator
     - Operator account creation
     - Role/permission assignment

3. Dashboards
   - 3.1 Operator Dashboard
     - Add / Edit / Remove Garage
     - View real-time occupancy per garage
   - 3.2 Driver Dashboard
     - Find parking (map search)
     - Select spot and pay

4. Reporting
   - 4.1 Occupancy Reporting
     - Generate occupancy graphs
     - Historical utilization trends
   - 4.2 Financial Reporting
     - Export financial reports
     - Revenue summary by garage


