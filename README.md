# SLTMobitel Voice Chatbot

React/Vite voice chatbot frontend. The app is configured for GitHub Pages at:

`https://helloanupa.github.io/sanbot-chatbot-Test/`

## Local development

1. Install dependencies:

   ```bash
   npm ci
   ```

2. Copy `.env.example` to `.env` and set the API and WebSocket URLs.

3. Start the development server:

   ```bash
   npm run dev
   ```

4. Verify the production build:

   ```bash
   npm run build
   npm run preview
   ```

## GitHub Pages deployment flow

1. Push the repository to GitHub on the `main` branch.
2. Open **Settings > Pages** in the repository.
3. Set **Source** to **GitHub Actions**.
4. Push a change to `main`, or run **Deploy to GitHub Pages** from the **Actions** tab.
5. Wait for the workflow to finish, then open the Pages URL above.

The workflow in `.github/workflows/deploy-pages.yml` installs dependencies, builds the Vite app, uploads `dist`, and deploys it automatically.

GitHub Pages hosts only the frontend. The backend at `VITE_API_BASE` and `VITE_WS_URL` must be publicly reachable over HTTPS/WSS and must allow the GitHub Pages origin in its CORS/WebSocket configuration. Microphone access also requires HTTPS, which the Pages URL provides.
