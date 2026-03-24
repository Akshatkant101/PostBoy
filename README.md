# PostBoy

PostBoy is a Postman-style API workspace built with Next.js, Prisma, and PostgreSQL.  
It supports REST request building, collections, workspaces, and realtime WebSocket testing in one UI.

## Features

- Workspace-based collaboration
- Collections and saved requests
- REST request editor (params, headers, body)
- Response viewer and request run history
- Realtime WebSocket testing with presets and message logs
- GitHub and Google auth via Better Auth
- AI helper integrations (Google/OpenAI SDKs)

## Tech Stack

- Next.js 15 (App Router)
- React 19 + TypeScript
- Prisma ORM
- PostgreSQL (Docker)
- Better Auth
- Tailwind CSS + Radix UI
- React Query + Zustand

## Getting Started

### 1) Clone and install

```bash
git clone https://github.com/Akshatkant101/PostBoy.git
cd PostBoy
npm install
```

### 2) Configure environment

Create a `.env` file in the project root and add:

```env
DATABASE_URL=
BETTER_AUTH_SECRET=
BETTER_AUTH_URL=http://localhost:3000

GITHUB_CLIENT_ID=
GITHUB_CLIENT_SECRET=

GOOGLE_CLIENT_ID=
GOOGLE_CLIENT_SECRET=

NEXT_PUBLIC_APP_URL=http://localhost:3000

GOOGLE_GENERATIVE_AI_API_KEY=
```

### 3) Start database and app

The dev command starts PostgreSQL using Docker Compose and then runs Next.js:

```bash
npm run dev
```

PostgreSQL defaults from `docker-compose.yml`:

- User: `postgres`
- Password: `postgres`
- DB: `postgres`
- Host port: `5433`

### 4) Run Prisma migrations

In another terminal:

```bash
npx prisma migrate deploy
```

For local development, you can also use:

```bash
npx prisma migrate dev
```

## Scripts

- `npm run dev` - start DB (Docker) and run local dev server
- `npm run build` - production build
- `npm run start` - start production server
- `npm run lint` - run ESLint

## Project Structure

- `src/app` - route segments and app layouts
- `src/modules` - feature modules (workspace, collections, request, realtime, auth)
- `src/components` - shared and UI components
- `src/lib` - shared utilities, auth, env, db helpers
- `prisma` - Prisma schema and migrations

## Notes

- Make sure Docker Desktop is running before `npm run dev`.
- Update OAuth callback URLs in provider settings to match your app URL.

