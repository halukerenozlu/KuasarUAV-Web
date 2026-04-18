# 🚁 UAV Website

A modern web application for presenting UAV projects, vehicles, competitions, and sponsors.

Built with **Next.js, React, Prisma ORM and Tailwind CSS. Made for Dumlupinar University Kuasar UAV Team.**

> Status: The project has reached a “good enough” state for its original purpose.  
> No further development is currently planned.

## ✨ Features

- ⚡ Next.js App Router for modern, file-based routing
- 🎨 Tailwind CSS for responsive, utility-first styling
- 🧱 (Optional) shadcn/ui components for a consistent UI layer
- 🗄 Prisma ORM with PostgreSQL (running in Docker)
- 📱 Fully responsive layout (mobile, tablet, desktop)
- Structured sections for:
  - Home
  - Vehicles
  - Competitions
  - Sponsors
  - Contact

## 🧰 Tech Stack

- [Next.js](https://nextjs.org/)
- [React](https://react.dev/)
- [TypeScript](https://www.typescriptlang.org/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Prisma ORM](https://www.prisma.io/)
- [PostgreSQL](https://www.postgresql.org/) (via Docker)
- [shadcn/ui](https://ui.shadcn.com/) (if used in components)
- [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts)  
  (currently using the **default font configuration**)

## Database Diagram

![Database Diagram](./public/screenshots/db_diagram.png)

## 🖼 Screenshots

![Home Hero Page](./public/screenshots/heroSection.png)

![Team Page](./public/screenshots/team.png)

![Login Page](./public/screenshots/login.png)

![Admin Panel Page](./public/screenshots/panel.png)

🚀 Getting Started

Even though the project is not under active development, you can still run it locally.

1. Clone the repository

```
git clone <repository-url>
cd <project-folder>
```

1. Install dependencies

```
npm install
# or
pnpm install
# or
yarn
# or
bun install
```

1. Run PostgreSQL with Docker

Make sure you have Docker installed and running, then start a PostgreSQL container
(or use your existing setup).

Example (adjust values as needed):

```
docker run --name ihadb -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=postgres \
  -e POSTGRES_DB=ihadb -p 5432:5432 -d postgres
```

Set your DATABASE_URL in .env:

```
DATABASE_URL="postgresql://postgres:postgres@localhost:5432/ihadb"
```

Run Prisma migrations (if applicable):

```
npx prisma migrate deploy
# or
npx prisma migrate dev
```

4. Start the development server

```
npm run dev
# or
pnpm dev
# or
yarn dev
# or
bun dev
```

Then open:

👉 http://localhost:3000

# ⚙️ Configuration Notes

Some behavior depends on configuration files:

- app/robots.ts
  Controls how search engines see and index the site.
  To make the site publicly visible in search engines, this file must be adjusted.

- middleware.ts
  Handles features such as authentication, route protection, or redirects.
  This file needs to be properly configured before any real production use.

- Fonts
  The project currently uses the default font configuration via next/font.
  If you want a specific font family, you will need to update that configuration.

# ⚠️ Important Warnings & Limitations

## Please read carefully before using this project in a real environment:

### Account delete button is NOT active

- The account deletion button is present in the UI.

- It is not wired to any backend logic.

- Do not rely on it for actual account removal.

### Search engine visibility (robots.ts)

- The site is not automatically configured to be fully indexable.

- To make it discoverable via search engines,
  you must update app/robots.ts accordingly.

### Default font

- The site uses the default font setup.

- No custom typography system has been configured.

### middleware.ts must be configured

- The middleware.ts file is required for proper behavior in areas like auth or protected routes.

- Review and configure it before treating this as a production-ready app.

### Multiple admins are NOT supported

- The current implementation only supports a single admin.

- Multiple admin accounts are not supported.

- Adding multi-admin support would require changes in auth logic and database schema.

# 🌍 Deployment

The app was designed to be deployable on platforms like Vercel or similar.

Typical flow:

- Push the repository to GitHub / GitLab.

- Connect the repo to a hosting platform (e.g. Vercel).

- Configure environment variables (e.g. DATABASE_URL).

- Ensure your PostgreSQL instance (Docker / managed DB) is reachable.

- Trigger a build & deploy.

For more details, refer to the Next.js deployment docs.

# 📌 Project Status

- This project was created for the Dumlupinar University Kuasar UAV Team and has fulfilled its main purpose.

- No new features are planned.

- The repository is kept mainly for reference, portfolio, and learning purposes.

- If you clone or extend it for your own needs, feel free to adapt the stack, design, and logic as you like.
