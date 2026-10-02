# Smart Parking Platform: Project Document
**Version:** 0.4
**Prepared by:** WE ARE $oftware ¢orp
**Date:** 09/09/2026

## Table of Contents
- [1. Research: Existing Software Landscape](#1-research-existing-software-landscape)
- [2. Vision and Scope](#2-vision-and-scope)
- [3. Software Requirements Specification](#3-software-requirements-specification-srs)
- [4. Project Planning](#4-project-planning)
- [5. Risk, Quality, and Communication Management](#5-risk-quality-and-communication-management)


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


<img width="1916" height="973" alt="image" src="https://github.com/user-attachments/assets/ad01ac9f-31f2-4408-900c-40d97cb5707f" />
Figure 1: Sprint 1 board showing the active sprint's To Do items.

<img width="1916" height="978" alt="image" src="https://github.com/user-attachments/assets/5de6f9e5-6320-4b5b-a4c3-8fcdf2e76399" />
Figure 2: Product backlog showing the remaining items not yet pulled into Sprint 1.

## 5. Risk, Quality, and Communication Management

### 5.1 Risk Register

| ID | Category | Description | Probability | Impact | Risk Level | Owner | Response Strategy | Status/Notes |
|----|----------|--------------|-------------|--------|------------|-------|--------------------|---------------|
| R1 | Technical | Parking sensor/API integration fails to report real-time occupancy reliably | Moderate (3) | Major (4) | High | Backend Lead | Mitigate — build polling fallback + cached last-known state | Open |
| R2 | Technical | Third-party payment processor API has downtime or breaking changes | Low (2) | Major (4) | Medium | Backend Lead | Transfer — rely on processor's SLA; add retry/queue logic | Open |
| R3 | Technical | Mobile app fails on older iOS/Android versions | Moderate (3) | Minor (2) | Medium | Mobile Dev | Mitigate — define minimum supported OS versions early | Open |
| R4 | Technical | Database can't scale to support 5,000+ concurrent users (per NFR1) | Low (2) | Catastrophic (5) | Medium | Backend Lead | Mitigate — load testing before launch; cloud auto-scaling | Open |
| R5 | Schedule | Garage hardware/sensor vendor delays installation past planned date | Moderate (3) | Major (4) | High | Project Manager | Accept — build schedule buffer into timeline | Open |
| R6 | Schedule | Operator dashboard and driver app development dependencies slip (per WBS) | Moderate (3) | Moderate (3) | Medium | Project Manager | Mitigate — parallelize independent workstreams | Open |
| R7 | Schedule | City compliance/legal review takes longer than expected | Moderate (3) | Major (4) | High | Project Manager | Accept — submit compliance docs early in parallel with dev | Open |
| R8 | Schedule | Sprint 1 scope underestimated, pushing Sprint 2 start | Low (2) | Moderate (3) | Low | Scrum Master | Mitigate — track velocity after Sprint 1, adjust Sprint 2 scope | Open |
| R9 | Financial | Cloud hosting costs exceed budget due to higher-than-expected usage | Moderate (3) | Moderate (3) | Medium | Finance Lead | Mitigate — set usage alerts/budget caps on cloud provider | Open |
| R10 | Financial | City funding/contract renewal delayed, affecting payroll | Low (2) | Catastrophic (5) | Medium | Project Manager | Transfer — negotiate milestone-based payment terms in contract | Open |
| R11 | Financial | Third-party API/licensing costs increase mid-project | Low (2) | Minor (2) | Low | Finance Lead | Accept — minor cost, absorb into budget | Open |
| R12 | People | Key developer leaves mid-project (turnover) | Moderate (3) | Major (4) | High | Project Manager | Mitigate — maintain documentation, cross-train team members | Open |
| R13 | People | Team conflict over technical direction (e.g., architecture disagreements) | Low (2) | Moderate (3) | Low | Scrum Master | Mitigate — regular retrospectives, clear decision-making process | Open |
| R14 | People | Skill gap — team lacks experience with real-time data/map APIs | Moderate (3) | Moderate (3) | Medium | Project Manager | Mitigate — allocate time for research spikes/training | Open |

*Risk Level derived from the course's Risk Matrix (Probability × Impact).*

### 5.2 Communication Plan

**Meeting Cadence**

| Meeting | Frequency | Attendees | Purpose |
|---------|-----------|-----------|---------|
| Daily Stand-up | Daily | Dev team | Short status sync — what was done, what's next, blockers |
| Sprint/Progress Meeting | Bi-weekly | Dev team + Scrum Master | Deeper check-in on sprint progress, backlog grooming |
| Sprint Review | End of each sprint | Full team + Product Owner | Demo completed work, gather feedback |
| Stakeholder/Sponsor Meeting | Monthly | Project Manager, city stakeholders | Big-picture progress update, budget/timeline check-in |

**Reporting Methods by Audience**

- **Executives / City Stakeholders:** High-level status reports and dashboards — overall timeline, budget burn, key risks, milestone progress (no technical detail).
- **Developers / Technical Team:** Detailed task-level updates via the Jira board (backlog, sprint board, burndown).
- **Operators / End Users (future phase):** Release notes and demo videos when new features ship.

**Team Size & Communication Channels**

Using the formula from class — n(n-1)/2 — for a team of 6 (PM, Scrum Master, 2 backend devs, 1 mobile dev, 1 QA):
6(6-1)/2 = **15 potential communication channels**. This is why structured cadences (stand-ups, sprint reviews) and a single source of truth (Jira + GitHub) are used instead of ad hoc one-off conversations.
