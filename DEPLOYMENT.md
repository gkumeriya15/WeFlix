# Deployment Guide

This project is a React application built with Vite and Tailwind CSS. It is configured for deployment on both **Vercel** and **Cloudflare (Pages or Workers Assets)**.

## Prerequisites

Before deploying, ensure you have the following API keys and configuration values:

### TMDB (The Movie Database)
- `VITE_TMDB_API`: Your TMDB API Key.
- `VITE_BASE_URL`: Usually `https://api.themoviedb.org/3`.

### Firebase
- `VITE_FIREBASE_API_KEY`
- `VITE_FIREBASE_AUTH_DOMAIN`
- `VITE_FIREBASE_PROJECT_ID`
- `VITE_FIREBASE_STORAGE_BUCKET`
- `VITE_FIREBASE_MESSAGING_SENDER_ID`
- `VITE_FIREBASE_APP_ID`
- `VITE_FIREBASE_MEASUREMENT_ID`

---

## Deploying to Vercel

1. **Connect Repository**: Push your code to a Git provider and connect it to Vercel.
2. **Framework Preset**: Vercel should automatically detect **Vite**.
3. **Build Settings**:
   - Build Command: `npm run build`
   - Output Directory: `dist`
4. **Environment Variables**: Add all variables in the Vercel dashboard.
5. **SPA Routing**: The included `vercel.json` file handles SPA routing.

---

## Deploying to Cloudflare

This repository is optimized for Cloudflare's **Workers Assets** (the modern deployment model for frontend apps on Cloudflare).

### Option A: Manual/CLI Deployment (using Wrangler)
1. Install dependencies and build: `npm install && npm run build`
2. Deploy using Wrangler: `npx wrangler deploy`
   - The included `wrangler.jsonc` ensures that the `dist` directory is uploaded and SPA routing is enabled.

### Option B: Git-based Deployment (Cloudflare Pages dashboard)
1. Connect your Git repository in the Cloudflare dashboard.
2. **Build Settings**:
   - Framework Preset: **Vite**
   - Build Command: `npm run build`
   - Build Output Directory: `dist`
3. **Environment Variables**: Add all variables in the dashboard.
4. **SPA Routing**: The included `public/_redirects` file ensures routing works correctly.

> **Note on Vite 8**: This project uses **Vite 8** for full compatibility with Cloudflare's latest deployment tools.

---

## Verification

After deployment, check the following:
- **Authentication**: Ensure Firebase login and signup work correctly.
- **Routing**: Navigate to various pages (Movies, TV Shows, Search) and refresh the browser.
- **Data Fetching**: Verify that movie and TV show data are loading from TMDB.
