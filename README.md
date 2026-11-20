# CI/CD Pipeline: Auto Deploy to Vercel (v2)

A minimal Next.js app used to practice a **Jenkins pipeline that deploys to Vercel**.

## Tech Stack

Next.js · React · TypeScript · Tailwind CSS · Jenkins (Windows agent) · Vercel CLI

## How the pipeline works (`Jenkinsfile`)

A declarative pipeline that uses `bat` steps, so it expects a **Windows** Jenkins agent:

| Stage | Command |
|---|---|
| Install Dependencies | `npm install` |
| Run Tests | placeholder (skipped for now) |
| Build Project | `npm run build` |
| Deploy to Vercel | `npx vercel --prod --yes --token=%VERCEL_TOKEN%` |

## Prerequisites

- A Jenkins server with a Windows agent that has Node.js and npm
- A Vercel account and access token
- A Jenkins **Secret text** credential with the ID `vercel-token` that contains the Vercel token

## Run locally

```bash
git clone https://github.com/KahafSameer/ci-cd-pipeline-auto-deploy-vercel_v2.git
cd ci-cd-pipeline-auto-deploy-vercel_v2
npm install
npm run dev      # http://localhost:3000
```

| Command | Description |
|---|---|
| `npm run dev` | Development server |
| `npm run build` | Production build |
| `npm run start` | Serve the production build |
| `npm run lint` | Run ESLint |
