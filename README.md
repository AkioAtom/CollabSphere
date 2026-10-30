# CollabSphere

A fullstack real-time collaboration platform built with Next.js on the frontend and Express + Socket.IO on the backend.

> **Status:** Early development. The project is currently a working scaffold — the frontend renders a starter page and the backend exposes a minimal Express API. Features listed below are in progress or planned.

## Tech Stack

### Frontend
- [Next.js 16](https://nextjs.org) (App Router)
- [React 19](https://react.dev)
- [TypeScript](https://www.typescriptlang.org)
- [Tailwind CSS 4](https://tailwindcss.com)

### Backend
- [Node.js](https://nodejs.org) + [Express 5](https://expressjs.com)
- [TypeScript](https://www.typescriptlang.org) (run with [tsx](https://github.com/privatenumber/tsx))
- [Prisma](https://www.prisma.io) (ORM)
- [Socket.IO](https://socket.io) (real-time communication)
- JWT (`jsonwebtoken`) + `bcrypt` (authentication)
- `cors`, `dotenv`

## Project Structure

```
CollabSphere/
├── backend/
│   ├── src/
│   │   ├── app.ts          # Express app setup and middleware
│   │   ├── server.ts       # Server entry point, routes, and listener
│   │   └── .env.example    # Environment variable template
│   ├── package.json
│   └── tsconfig.json
├── frontend/
│   ├── src/
│   │   └── app/
│   │       ├── layout.tsx  # Root layout and metadata
│   │       ├── page.tsx    # Home page
│   │       └── globals.css # Tailwind imports and theme tokens
│   ├── public/
│   ├── next.config.ts
│   └── package.json
├── .gitignore
└── README.md
```

## Getting Started

### Prerequisites

- Node.js 20+ (developed against Node 26)
- npm 10+
- A database supported by Prisma (e.g. PostgreSQL, MySQL, or SQLite)

### 1. Clone the repository

```bash
git clone <repository-url>
cd CollabSphere
```

### 2. Set up the backend

```bash
cd backend
npm install
```

Create `backend/.env` from the example file and fill in your values:

```bash
cp src/.env.example .env
```

Expected variables (adjust to match your setup):

```env
PORT=5000
DATABASE_URL="postgresql://user:password@localhost:5432/collabsphere"
JWT_SECRET=your-secret-key
CLIENT_ORIGIN=http://localhost:3000
```

Generate the Prisma client and apply migrations once the schema is defined:

```bash
npx prisma generate
npx prisma migrate dev
```

Start the development server:

```bash
npm run dev
```

The API runs at **http://localhost:5000**.

### 3. Set up the frontend

In a separate terminal:

```bash
cd frontend
npm install
npm run dev
```

The app runs at **http://localhost:3000**.

## Available Scripts

### Backend (`backend/`)

| Command | Description |
| --- | --- |
| `npm run dev` | Start the server in watch mode with `tsx` |
| `npm test` | Placeholder — no tests configured yet |

### Frontend (`frontend/`)

| Command | Description |
| --- | --- |
| `npm run dev` | Start the Next.js development server |
| `npm run build` | Create a production build |
| `npm start` | Serve the production build |
| `npm run lint` | Run ESLint |

## API

Current endpoints (backend, port `5000`):

| Method | Path | Description |
| --- | --- | --- |
| `GET` | `/` | Health check — returns `Hello from server` |
| `POST` | `/` | Echoes the JSON request body back as `{ data }` |

These are placeholders and will be replaced by real application routes.

## Roadmap

- [ ] Define the Prisma schema and database models
- [ ] Add user registration and login (JWT + bcrypt)
- [ ] Implement protected routes and auth middleware
- [ ] Add real-time collaboration with Socket.IO
- [ ] Build workspace/project UI in the frontend
- [ ] Add tests and CI

## Contributing

1. Fork the repository.
2. Create a feature branch: `git checkout -b feat/my-feature`.
3. Commit your changes: `git commit -m "feat: add my feature"`.
4. Push the branch: `git push origin feat/my-feature`.
5. Open a pull request.

## License

No license has been specified for this project yet.
