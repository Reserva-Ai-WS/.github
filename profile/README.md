<div align="center">

# 📅 RESERVA AÍ

### WEG Room, Tablet and Notebook Booking — all in one place

*No more email chains, scattered spreadsheets, or scheduling clashes.*

</div>

---

## 🎯 About the project

**RESERVA AÍ** is a web system that centralizes and simplifies the booking of **CentroWEG rooms** and the lending of **notebooks** and **tablets**, used by the **WEG** and **SENAI** teams.

With it, the room and the equipment are reserved in a single request, and everyone can instantly see what is available.

## 🧩 The problem

Scheduling today is manual and decentralized, which leads to:

- ⚠️ Time conflicts and duplicate room bookings
- 🔍 Difficulty tracking **who has** each notebook and tablet
- 🔐 Risks to asset security and control
- 📧 Heavy manual work, communication failures, and data loss

## 💡 Delivered value

- ✅ No more time clashes or duplicate bookings
- ✅ Instant visibility of what is available
- ✅ Tracking of who holds each device and when it is due back
- ✅ Less rework for the team and stronger control over assets
- ✅ Room and equipment secured in the same request

## 👥 Who uses it

> Students are **not** registered in the system.

| Profile | What they can do |
|---|---|
| **WEG team** | Register and book CentroWEG rooms, manage notebooks, headphones, and tablets, and track who holds the equipment. Gives the **final approval** on room bookings. |
| **SENAI team** | Book CentroWEG rooms and manage tablets (registration, removal, and availability). |
| **SENAI instructors** | Request rooms (reviewed first by the Manager) and request tablets and notebooks when needed. |
| **Manager** | Reviews, approves, or denies the room requests made by instructors, and can give a reason for a denial. |
| **Administrator** | Registers, searches, edits, removes (reversible within 30 days), and manages all users. |

## 🛠️ Technologies

### Backend
- **Spring Boot** — chosen framework
- **Event-Driven Microservices** — Room, Tablet, Notebook, and Notifications
- **Apache Kafka** — event streaming between services
- **SSE (Server-Sent Events)** — automatic server-to-frontend updates
- **MVC + TDD** — Domain-Driven Development + Test-Driven Development
- **Spring Security** — OAuth2 + JWT + Google Sign-In
- **AWS DynamoDB** — NoSQL database

### Frontend
- **Next.js**
- **React**
- **TypeScript**
- **TailwindCSS**

### Tools
- **WebStorm** — Frontend IDE
- **IntelliJ IDEA** — Backend IDE
- **pnpm** — package manager

### Project management
- **Kanban** on GitHub Projects

## 🔄 Room approval flows

There are two approval flows, depending on who makes the request.

**SENAI instructors** — the request goes through the Manager before reaching WEG:

```
Instructor requests  →  Manager reviews  →  WEG gives final approval  →  User is notified
```

**WEG and SENAI teams** — the request goes straight to WEG:

```
WEG / SENAI team requests  →  WEG gives final approval  →  User is notified
```

## 👨‍💻 Team

| Name |
|---|
| Enzo Venturi |
| Gabriel Behling |
| Luigi Barbieri Lombardo |
| Murilo Heitor Joly |
| Vinicius Zick |

---

<div align="center">

Made with 💙 by the **Reserva-Ai-WS** team

</div>
