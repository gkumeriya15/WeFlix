# Deployment Guide

This project is a React application built with Vite and Tailwind CSS. It is configured for deployment on both **Vercel** and **Cloudflare Pages**.

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

1. **Connect Repository**: Push your code to a Git provider (GitHub, GitLab, or Bitbucket) and connect it to Vercel.
2. **Framework Preset**: Vercel should automatically detect **Vite**.
3. **Build Settings**:
   - Build Command: `npm run build`
   - Output Directory: `dist`
4. **Environment Variables**: Add all the variables listed above in the Vercel dashboard under Project Settings > Environment Variables.
5. **SPA Routing**: The included `vercel.json` file handles SPA routing by rewriting all requests to `index.html`.

---

## Deploying to Cloudflare Pages

1. **Connect Repository**: Connect your Git repository to Cloudflare Pages via the dashboard.
2. **Build Settings**:
   - Framework Preset: **Vite**
   - Build Command: `npm run build`
   - Build Output Directory: `dist`
3. **Environment Variables**: Go to Settings > Variables and Secrets and add all the environment variables listed above. Note that for Cloudflare Pages, these must be set for both the **Production** and **Preview** environments.
4. **SPA Routing**: The included `public/_redirects` file ensures that all routes are correctly handled by the React application's router.

---

## Verification

After deployment, check the following:
- **Authentication**: Ensure Firebase login and signup work correctly.
- **Routing**: Navigate to various pages (Movies, TV Shows, Search) and refresh the browser to confirm SPA routing is functioning.
- **Data Fetching**: Verify that movie and TV show data are loading correctly from TMDB.
