<div align="center">

# Reserva Aí

Reserva Aí is a web system for booking the CentroWEG rooms and lending out notebooks, tablets and headphones. It is built for the WEG and SENAI teams.

</div>

## The problem

Right now, scheduling is done by hand and spread across emails and spreadsheets. This causes double bookings and time conflicts in the rooms, and it makes it hard to know who currently has a given device, which puts the equipment at risk.

## What it solves

The system puts everything in one place. Someone can book a room or a device, see what is free right away, and follow each request until it is approved. Approved bookings show up on a shared calendar, and every decision is sent by email. The goal is to cut down on manual work and miscommunication, and to keep better control over WEG's assets.

## Who uses it

Students are not registered in the system.

| Profile | What they can do |
|---|---|
| `WEG` | Registers and edits rooms, manages devices and gives the final approval on every room booking. Bookings made by WEG are approved right away. |
| `MANAGEMENT` | Manages devices and reviews the room requests made by SENAI users, approving or denying them (a reason is required to deny). |
| `SENAI` | Requests rooms and devices and follows their own bookings. |
| `ADMIN` | Registers and removes users. New users get a temporary password by email and must change it on first login. |

## Room approval flow

Every room request ends with WEG. Where it starts depends on who makes it:

```
SENAI       -> MANAGEMENT -> WEG (final approval) -> user is notified by email
MANAGEMENT  ->               WEG (final approval) -> user is notified by email
WEG         ->               approved right away
```

Bookings can be made from 07:30 to 21:45, Monday to Friday, and never for a date or time that has already passed.

## Run it locally

You only need [Docker Desktop](https://www.docker.com/products/docker-desktop/). This starts the database, the API and the web app:

```bash
curl -O https://raw.githubusercontent.com/Reserva-Ai-WS/ReservaAi-core/develop/compose.yaml
docker compose up -d
```

Then open **http://localhost:3000** and sign in with `weg@reservaai.local` / `Senha@123`. The other test users are listed in the [ReservaAi-core](https://github.com/Reserva-Ai-WS/ReservaAi-core) README.

## Repositories

| Repository | What it is |
|---|---|
| [ReservaAi-core](https://github.com/Reserva-Ai-WS/ReservaAi-core) | REST API (Spring Boot) and the `compose.yaml` that runs the whole system |
| [ReservaAi-frontend](https://github.com/Reserva-Ai-WS/ReservaAi-frontend) | Web app (Next.js) |

## Technologies

**Backend**
- Java 21 and Spring Boot 4
- Modular monolith with Spring Modulith (modules: identity, room, devices, reservations and notification), communicating through events
- Spring Security with JWT
- Spring Data JPA and Flyway
- PostgreSQL (AWS RDS in production)
- Email notifications over SMTP
- Swagger UI (springdoc) and Javadoc

**Frontend**
- Next.js 16 (App Router) and React 19
- TypeScript
- Tailwind CSS 4, shadcn/ui and Radix UI
- Jest and Testing Library

**Infrastructure**
- Docker images published to Docker Hub by GitHub Actions
- Backend on AWS EC2, frontend on Netlify

**Tools**
- IntelliJ IDEA (backend) and WebStorm (frontend)
- Kanban board on GitHub Projects

## Team

- Enzo Venturi
- Gabriel Behling
- Luigi Barbieri Lombardo
- Murilo Heitor Joly
- Vinicius Zick

<div align="center">
Made with ❤️ by the Reserva Aí team!
</div>
