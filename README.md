# YouTube Downloader - Frontend

React-based web interface for downloading YouTube videos.

## Features

- Modern, responsive UI built with React and Tailwind CSS
- Video preview with thumbnail and duration
- Format selection (MP4, MP3, WEBM)
- Quality options
- Download progress tracking
- Clean, intuitive interface

## Setup

1. Install dependencies:
```bash
npm install
```

## Development

Start the development server:
```bash
npm start
```

The app will open at `http://localhost:3000`

## Build

Create a production build:
```bash
npm run build
```

## Available Scripts

- `npm start` - Runs the app in development mode
- `npm run build` - Builds the app for production
- `npm test` - Runs the test suite
- `npm run eject` - Ejects from Create React App (one-way operation)

## Configuration

- Default API: If no env var is set, the app uses `http://localhost:5000`.
- Recommended: Set `REACT_APP_API_BASE_URL` to your backend URL.

Local development:
```bash
echo REACT_APP_API_BASE_URL=https://ytsuite-702749419835.asia-south1.run.app > .env.local
npm start
```

Netlify: Add an environment variable `REACT_APP_API_BASE_URL` with your backend URL, or keep it in `netlify.toml`.

## Deploy: GitHub Pages

This repo is set up to deploy with GitHub Actions to GitHub Pages.

1. Repository settings:
	- Set Pages source to the `gh-pages` branch (root), or choose "GitHub Actions" if using the newer Pages flow.

2. Secrets (Repository → Settings → Secrets and variables → Actions):
	- `API_BASE_URL`: Your backend URL (e.g., `https://ytsuite-702749419835.asia-south1.run.app`).
	- `PAGES_CNAME` (optional): Your custom domain (e.g., `example.com`). If set, the workflow will publish a CNAME file for Pages.

3. Homepage:
	- `package.json` `homepage` must match your GitHub Pages site URL, e.g., `https://<username>.github.io/<repo>`. This project is configured for `https://Keshavv-chauhan.github.io/YTsfront`.

4. Trigger deploy:
	- Push to `main`. The workflow builds and publishes to `gh-pages` automatically.

5. Verify:
	- Visit the Pages URL. If using a custom domain, ensure your DNS points to GitHub Pages and that the `PAGES_CNAME` secret is set.

Notes:
- CORS: Backend should allow your Pages domain. Current backend uses `CORS_ORIGIN=*`; you can tighten it to your domain later.
- Cookies: If YouTube requires cookies, pass them via headers from the client; see backend docs.

## Handling YouTube Bot Checks (Cookies)

Some videos require confirmation that you're not a bot. Use the built-in Settings panel to paste a YouTube `Cookie` header and enable it for requests.

Steps to copy your Cookie header:
- Open YouTube and sign in.
- Press F12 → Network → reload the page.
- Pick any request to `https://www.youtube.com/*`.
- In Request Headers, copy the value of `cookie:` (without the word `cookie:`).
- Paste into Settings → "YouTube Cookie Header" and enable the toggle.

Security note: Cookies grant account access. Keep them private. They expire; refresh if you see errors.

## Technologies

- React 19
- Tailwind CSS
- Lucide React (icons)
- Create React App
