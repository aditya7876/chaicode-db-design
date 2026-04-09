#Comic-Con Parking System

The system is designed to efficiently manage vehicle entry, parking allocation, reserved categories, sessions, and payments.

---

## 📌 Problem Statement

A large event venue hosts thousands of visitors across multiple days. Vehicles such as bikes, cars, SUVs, cabs, and EVs arrive and require structured parking.

The system must handle:
- Vehicle entry and exit tracking
- Parking spot allocation
- Reserved parking (VIP, staff, exhibitors, EV, cosplayers)
- Multi-zone and multi-level parking
- Ticket generation
- Payment tracking
- Real-time parking availability

---

## 🧠 Key Features of the Design

- Supports **multiple entries per vehicle**
- Tracks **parking sessions with entry & exit timestamps**
- Allows **reuse of parking spots**
- Handles **vehicle types and spot compatibility**
- Supports **reserved parking categories**
- Tracks **zone and level hierarchy**
- Maintains **payment records per session**
- Identifies **currently parked vehicles**

---

## 🏗️ Entities Included

- **Vehicle**
- **Vehicle Category**
- **Parking Zone / Level**
- **Parking Spot**
- **Spot Category (Reserved / Normal / EV)**
- **Access Category (VIP, Staff, Exhibitor, Cosplayer)**
- **Parking Ticket**
- **Parking Session**
- **Payment**

---

## 🔗 Relationships Overview

- One vehicle → multiple parking sessions  
- One parking spot → multiple sessions over time  
- One zone → multiple parking spots  
- One session → one ticket and one payment  
- Access categories define special permissions  
