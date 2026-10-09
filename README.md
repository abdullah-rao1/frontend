# Smart RAG Lite — Frontend

A small React + Vite app for the Smart RAG Lite backend: sign up, log in, upload documents,
ask questions, and see each answer with its sources, the AI validation result, and the
pipeline steps that produced it.

No UI framework and no animation libraries: plain CSS in `src/styles.css`.

## Files

```
src/
  api.ts                    every backend call + where the backend URL comes from
  App.tsx                   routes: /login, /signup, /chat, /chat/:id
  pages/AuthPage.tsx        login + signup form
  pages/ChatPage.tsx        chats sidebar, upload, documents, questions
  components/AnswerCard.tsx answer, "Checked by AI" stamp, sources, pipeline steps
  styles.css
```

## Run locally

Start the backend first (on port 8000), then:

```
npm install
npm run dev
```

Open http://localhost:5173. In dev, Vite forwards `/api` requests to `http://127.0.0.1:8000`
(see `vite.config.ts`), so no environment variable is needed.

## Deploy on Vercel

See the top-level `README.md` of this bundle. In short: import the repo in Vercel (Vite preset is
detected from `vercel.json`), set `VITE_API_BASE_URL` to the Railway backend URL, deploy, then add
the Vercel URL to the backend's `CORS_ORIGINS`.
