# Jambo Hotel Management System

## Project Overview

The **Jambo Hotel Management System** is a multi-page web application designed to streamline hotel front-desk and housekeeping operations.

The system allows hotel staff to efficiently manage:

- Guest check-ins
- Room assignments
- Guest check-outs
- Service requests
- Housekeeping tasks
- Room availability tracking

The application supports **two user roles**:

### 1. Receptionist
The receptionist can:

- Log into the system securely
- View all hotel rooms and their current status
- Check in guests and assign them to available rooms
- Capture guest details such as:
  - Legal occupant name
  - Number of occupants
  - Length of stay
  - Check-in date
- Check guests out
- Add service requests (e.g., cleaning, extra towels, food delivery)
- View occupant records
- Track which rooms are available, occupied, or need cleaning

---

### 2. Housekeeping Staff

Housekeeping staff can:

- Log into the system securely
- View rooms that require cleaning
- View rooms with pending service requests
- Mark rooms as cleaned once tasks are completed

---

# Project Scope

This project focuses on **internal hotel operations only**.

### Included Features

✔ Guest check-in and check-out  
✔ Room status management  
✔ Occupant data tracking  
✔ Service request management  
✔ Housekeeping task management  
✔ Session-based login authentication  
✔ Local JSON-based data storage

### Not Included

✘ Online room booking  
✘ Payment processing  
✘ Customer-facing portal  
✘ Database integration (uses JSON files instead)

---

# Technologies Used

## Backend

- **Node.js**
- **Express.js**

## Frontend

- **Handlebars (HBS)** – templating engine
- **Bootstrap 5** – UI styling and responsive design
- HTML/CSS

## Authentication

- **express-session** for session management

## Data Storage

The application stores data locally using JSON files:

- `users.json` → system users and login credentials
- `rooms.json` → room information and room status
- `occupants.json` → guest check-in records
- `inventory.json` → hotel inventory items

---

# Features Implemented

## Login System

Users log in using username and password.

Session management ensures:

- Users stay logged in while navigating pages
- Unauthorized users cannot access restricted pages
- Access is controlled based on user role

---

## Receptionist Dashboard

Displays room cards showing:

- Room number
- Room type
- Occupancy status
- Cleaning status
- Service request notifications

Available actions:

- **Check In** (opens modal form)
- **Check Out**
- **Add Service Request**

---

## Occupants Page

Displays all checked-in guest information:

- Guest name
- Assigned room
- Room type
- Check-in date
- Automatically calculated check-out date

---

## Housekeeping Dashboard

Displays rooms that:

- Need cleaning
- Have pending service requests

Allows staff to:

- Mark tasks as complete

---

# Session Handling

The project uses **express-session** to manage user login sessions.

Example:

```javascript
app.use(session({
  secret: "jambohotel_secret_key",
  resave: false,
  saveUninitialized: false
}));
