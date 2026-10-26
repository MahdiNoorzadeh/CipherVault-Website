# CipherVault Website

A standalone marketing website for CipherVault, built with Vue 3 and Vite. This repository is intentionally separate from the Electron desktop application.

## Stack

- Vue 3
- Vite
- Plain CSS (responsive layout; no UI framework required)
- Vercel-ready static build

## Run locally

```bash
npm install
npm run dev
```

## Production build

```bash
npm run build
npm run preview
```

Vite outputs the static site to `dist/`.

## Deploy to Vercel

1. Push this website folder to a new GitHub repository (for example, `CipherVault-Website`).
2. Import that repository in Vercel.
3. Use the Vite preset, with `npm run build` as the build command and `dist` as the output directory.
4. Deploy. No environment variables are required for the initial static site. The official application icon is served from `public/ciphervault-icon.png`.

## Official product links

- Desktop app repository: https://github.com/MahdiNoorzadeh/CipherVault
- Releases: https://github.com/MahdiNoorzadeh/CipherVault/releases
- Setup guide: https://github.com/MahdiNoorzadeh/CipherVault/blob/main/SETUPGUIDE.md
- README: https://github.com/MahdiNoorzadeh/CipherVault#readme

## Product-accuracy notes

The hero uses the official CipherVault application icon and abstract security styling; it does not present a fabricated desktop-interface screenshot as the real app. The palette follows the desktop app theme: midnight charcoal, violet primary accents, and lavender highlights. Add verified screenshots from the current release in the content sections when available. Product statements are based on the desktop repository README; avoid adding claims that aren't supported by the implementation or a security audit.

## Isolation rule

Keep this project in its own directory and GitHub repository. Do not copy its files into the desktop application's repository.
