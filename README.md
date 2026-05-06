# Team Task Manager

A full-stack web app for creating projects, assigning tasks, tracking status, and managing team access with Admin/Member roles.

## Features

- Signup and login with password hashing
- First registered user becomes `Admin`; later users become `Member`
- REST APIs for auth, users, projects, tasks, and dashboard metrics
- Role-based access control:
  - Admins can manage all projects, users, roles, and tasks
  - Members can access projects they belong to
  - Project owners can manage their own projects
- Project membership relationships
- Task assignment to project members only
- Status tracking: `todo`, `in_progress`, `review`, `done`
- Dashboard totals, status counts, overdue tasks, and personal open tasks
- Persistent NoSQL-style JSON database

## Tech Stack

- Node.js HTTP server
- Vanilla JavaScript frontend
- JSON document database stored at `data/db.json`
- No external npm dependencies

## Local Setup

```bash
npm install
npm start
```

Open `http://localhost:3000`.

## Railway Deployment

1. Push this project to GitHub.
2. Create a new Railway project.
3. Select **Deploy from GitHub repo**.
4. Add this environment variable in Railway:

```bash
JWT_SECRET=use-a-long-random-production-secret
```

5. Railway will run:

```bash
npm start
```

The app listens on `process.env.PORT`, which Railway provides automatically.

## API Overview

### Auth

- `POST /api/auth/signup`
- `POST /api/auth/login`
- `GET /api/me`

### Users

- `GET /api/users`
- `PATCH /api/users/:id/role`

### Projects

- `GET /api/projects`
- `POST /api/projects`
- `PATCH /api/projects/:id`
- `DELETE /api/projects/:id`

### Tasks

- `GET /api/tasks`
- `POST /api/tasks`
- `PATCH /api/tasks/:id`
- `DELETE /api/tasks/:id`

### Dashboard

- `GET /api/dashboard`

## Submission

- Live URL: add your Railway URL here after deployment
- GitHub repo: add your repository URL here
