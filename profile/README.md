<div align="center">
  
# Reserva Aí

Reserva Aí is a web system for booking the CentroWEG rooms and lending out notebooks and tablets. It is built for the WEG and SENAI teams.

</div>

## The problem

Right now, scheduling is done by hand and spread across emails and spreadsheets. This causes double bookings and time conflicts in the rooms, and it makes it hard to know who currently has a given notebook or tablet, which puts the equipment at risk.

## What it solves

The system puts everything in one place. Someone can book a room and reserve the equipment they need in the same request, see what is free right away, and check who has each device and when it is due back. The goal is to cut down on manual work and miscommunication, and to keep better control over WEG's assets.

## Who uses it

Students are not registered in the system.

| Profile | What they can do |
|---|---|
| WEG team | Register and book CentroWEG rooms, manage notebooks, headphones and tablets, and track who has the equipment. Gives the final approval on room bookings. |
| SENAI team | Book CentroWEG rooms and manage tablets (registration, removal and availability). |
| SENAI instructors | Request rooms, which are reviewed by the Manager first, and request tablets and notebooks when needed. |
| Manager | Reviews the room requests made by instructors, approves or denies them, and can give a reason when denying. |
| Administrator | Registers, searches, edits and removes users (removal can be undone within 30 days). |

## Technologies

**Backend**
- Spring Boot
- Event-driven microservices: Room, Tablet, Notebook and Notifications
- Apache Kafka
- Server-Sent Events (SSE) to push updates from the server to the frontend
- MVC with Domain-Driven Development and Test-Driven Development
- Spring Security with OAuth2, JWT and Google Sign-In
- AWS DynamoDB

**Frontend**
- Next.js
- React
- TypeScript
- TailwindCSS

**Tools**
- WebStorm (frontend) and IntelliJ IDEA (backend)
- pnpm
- Kanban board on GitHub Projects

## Room approval flows

Room requests follow one of two paths, depending on who makes them.

Requests from SENAI instructors go through the Manager before reaching WEG:

```
Instructor -> Manager -> WEG (final approval) -> User is notified
```

Requests from the WEG and SENAI teams go straight to WEG:

```
WEG / SENAI team -> WEG (final approval) -> User is notified
```

## Team

- Enzo Venturi
- Gabriel Behling
- Luigi Barbieri Lombardo
- Murilo Heitor Joly
- Vinicius Zick

<div align="center">
Made with ❤️ by the Reserva Aí team!!!
</div>
