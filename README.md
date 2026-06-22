# IDURAR ERP / CRM — (Imported copy)

This repository is an imported copy of the IDURAR open-source ERP / CRM application. It contains a Node.js + Express backend and a React (Vite) frontend with Ant Design and Redux.

This copy has a fresh git history (initial import). The original project is maintained by its authors — this repository preserves the source files but starts a new history.

## Purpose of this copy

- Provide a working local copy you can run or modify.
- Include a clear README and usage notes.

## Quick overview

- Backend: Node.js, Express, MongoDB (Mongoose) — code in ackend/
- Frontend: React + Vite, Ant Design — code in rontend/
- PDF templates: ackend/src/pdf/*.pug
- Setup scripts: ackend/src/setup (creates default admin and settings)

## Quick start (local)

1. Create a MongoDB database (cloud or local) and get the connection URI.
2. Copy the repository locally and create .env files in ackend/ and rontend/ as needed.

Backend

`powershell
cd backend
npm install
# Edit backend/.env and set DATABASE, JWT_SECRET, PUBLIC_SERVER_FILE, etc.
npm run setup   # creates initial admin and default settings
npm run dev     # starts backend on port 8888 (default)
`

Frontend

`powershell
cd frontend
npm install
# edit frontend/.env or use temp.env to set VITE_BACKEND_SERVER if needed
npm run dev     # starts frontend (Vite) on port 3000 (default)
`

Default credentials (created by setup):

- email: dmin@admin.com
- password: dmin123

Change these credentials immediately in production.

## Important environment variables

- DATABASE — MongoDB connection string (backend/.env)
- JWT_SECRET — secret used for signing JWT tokens
- PUBLIC_SERVER_FILE, VITE_FILE_BASE_URL — public file hosting for generated PDFs
- OPENAI_API_KEY — optional (used if OpenAI integrations used)

## License and compliance (AGPL)

The original project is licensed under the GNU Affero General Public License v3 (AGPL-3.0). That license applies to the source code in this repository. Key points:

- If you distribute the software or make it available as a network service (host it for others to use), you must provide the complete corresponding source code to users and keep the AGPL license.
- Keep the LICENSE file in the repository and include license notices in distributed copies.

If you plan to host a service based on this code, add a visible "Source code" link on the site and make your modified source available there.

## Notes and recommendations

- This copy was created with a fresh git history — original authorship and commit history from upstream are not present here. The AGPL license and copyright of original authors still apply.
- Review and update environment variables and secrets before running in production.
- Remove demo accounts and change default passwords before exposing to the internet.

## Contact / next steps

If you want, I can:
- push this cleaned import to your GitHub repository (you provided https://github.com/Prajwalthakare02/RAG-Document-Intelligence-Platform.git),
- keep the AGPL LICENSE file in place (recommended), and
- add a short LICENSE-COMPLIANCE.md explaining how to comply when hosting the app.

---

_This README was added/updated during import to provide usage and compliance guidance._
\n## Deployment\n\nThis repository is prepared for frontend deployment on Vercel (recommended) and backend deployment on a Node host (Render, Railway, or similar).\n\nFrontend (Vercel):\n- Connect this repository in the Vercel dashboard.\n- In Vercel Project Settings, set VITE_BACKEND_SERVER to your backend API URL (for example https://api.example.com).\n- Vercel will build the rontend folder via the root rontend/package.json using the default 
pm run build command.\n\nBackend (recommended hosts):\n- Deploy the ackend folder to a persistent Node host (Render, Railway, or Fly.io).\n- Required backend env vars: DATABASE (MongoDB URI), JWT_SECRET, PUBLIC_SERVER_FILE, and any SMTP/email credentials.\n\nIf you want, I can deploy the backend for you to Railway/Render and finish the Vercel setup steps (you will need to provide access tokens or approve the repo connections).
