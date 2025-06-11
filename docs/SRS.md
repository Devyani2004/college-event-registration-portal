### College Event Registration Portal
A web-based system to help college students easily register for events and allow administrators to manage participation records efficiently.

--- 

### Table of Contents
Introduction

Scope

Target Users

Technology Stack

Functional Requirements

Non-Functional Requirements

System Architecture

Modules Description

Use Case Overview

Database Design

Wireframes

Assumptions and Limitations
---

### Introduction
Purpose
This portal simplifies the event registration process for students while providing a centralized dashboard for administrators to manage and monitor participation. It replaces manual processes with a digital system to reduce errors and save time.

---

### Scope
Included Features
Student registration and login

Browsing upcoming/active events

Event registration with status tracking

Admin dashboard to monitor participation

Excluded Features
Payment integration

Automated email alerts

Event creation by students

---

### Target Users
Students: End users who register and attend events.

Admins: Authorized personnel who monitor and manage registration data.

---

### Technology Stack
Layer	Technology
Frontend	React.js, Bootstrap, CSS
Backend	Django or Node.js
Database	SQLite (dev), MySQL/PostgreSQL (prod)

---

### Functional Requirements
User registration and login with student/admin roles

Event listing (active/upcoming)

Student event registration (with duplicate prevention)

View registered events (student)

Admin dashboard to view participant list by event

---

### Non-Functional Requirements
Responsive UI (mobile and desktop)

Secure login with encrypted passwords

Page load time < 3 seconds

Modular, maintainable codebase

Reliable under standard college usage

---

### System Architecture

                      [Frontend: React.js + Bootstrap]
                              ⇅
                       [Backend API: Django]
                              ⇅
                        [Database: MySQL]


  ---
  
### Modules Description
User Module
Student sign-up/login/logout

View/manage personal event registrations

Event Module
List of upcoming/active events

Event details and registration interface

Admin Module
Admin login and dashboard

View participants per event

Authentication Module
Role-based access control (JWT or Django sessions)

Session management

---

### Use Case Overview
Students:
Sign Up → Login → Browse Events → Register → View Registered Events

Admins:
Login → Select Event → View Participant List

---

### Database Design
Tables
Users

id	Integer (PK)
name	String
email	String (unique)
password_hash	String
role	Enum (student/admin)

Events
Field	Type
id	Integer (PK)
title	String
description	Text
event_date	DateTime
venue	String

Registrations
Field	Type
id	Integer (PK)
user_id	FK → Users
event_id	FK → Events
registered_at	Timestamp

### Wireframes
 Login Page

 Student Dashboard (event cards + register buttons)

 Admin Dashboard (event dropdown + participant table)

 ---

 
### Assumptions and Limitations
Admin accounts will be created manually

No real-time notifications or email alerts

No payment gateway integration

Designed for internal college use only

Only basic client-side form validation implemented
