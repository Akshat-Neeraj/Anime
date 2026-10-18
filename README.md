<div align="center">

# 🌙 NightList

**Your personal media vault — anime, manga, movies, TV and games in one fast, private tracker.**

[**▶ Open the app**](https://akshat-neeraj.github.io/Anime/)

![No build step](https://img.shields.io/badge/build-none-8b5cf6?style=flat-square)
![Installable PWA](https://img.shields.io/badge/PWA-installable-22c55e?style=flat-square)
![One HTML file](https://img.shields.io/badge/app-one%20HTML%20file-f59e0b?style=flat-square)
![Local first](https://img.shields.io/badge/data-local--first-3b82f6?style=flat-square)

</div>

<!--
  SCREENSHOTS: add 2–3 PNGs to a /docs folder, then uncomment:
  <p align="center"><img src="docs/library.png" width="31%"> <img src="docs/detail.png" width="31%"> <img src="docs/wrapped.png" width="31%"></p>
  Tip: pick titles with SFW covers.
-->

---

## ✨ What it does

**Track everything**
- Grid, list and mood-board views · statuses (watching, watched, want, paused, dropped)
- Ratings you can display as `/10`, `★/5` or `%` · tags · notes (with spoiler blur) · rewatch counts
- Episode progress with a one-tap **+1 ep**
- Cover art fetched automatically
- 30-day **trash with undo**, a **duplicate scanner** with one-click merge, and bulk tagging

**Understand your taste**
- **Taste DNA** and a yearly **Wrapped**
- Watch **streaks**, a yearly goal, achievements and a drag-and-drop **tier list**
- A weekly **airing calendar** and a "Surprise me" picker weighted by what you actually like
- "What should I drop?" for shows you quietly abandoned

**Your data stays yours**
- Import from **MyAnimeList, AniList, Letterboxd** or JSON · export to MAL-compatible, JSON or CSV
- **Auto-save to a file** on your computer (Chrome / Edge)
- Installable **offline-first PWA** · keyboard shortcuts and screen-reader support

**Optional AI** *(bring your own free [Groq](https://console.groq.com) key)*
- AI Fill, a chat assistant, vibe search and recommendations
- "Where to watch" uses Groq's live-web-search model when your account has access, and falls back to plain search links when it doesn't — it never guesses a streaming site from memory

**Optional accounts**
- Email + password and Google sign-in, with your library synced to the cloud
- A per-account switch for **adult-tagged content — off by default**
- Admin tools for the site owner: user list, suspend / unsuspend, per-user title counts

---

## 🔒 Privacy

- **Local-first.** Without an account, your library lives only in your browser's storage. The only network calls are the ones you trigger (cover art, AI).
- **Your API keys stay in your browser.** AI requests go straight from your browser to Groq.
- **Accounts are isolated by the database.** Every table uses Row Level Security, so one user can't read another's library. The site admin can see usernames and how many titles each person has — **not** what's in anyone's library.
- **Adult-tagged titles are hidden unless an account opts in**, and they're excluded from every export and share. This is a content filter, not age verification.

---

## 🚀 Use it

1. Open **<https://akshat-neeraj.github.io/Anime/>**
2. Add titles — or import your list from MAL / AniList / Letterboxd.
3. *(Optional)* Add a Groq key in settings to switch on the AI features.
4. *(Optional)* Add it to your home screen to install it.

---

## 📁 What's in the repo

| File | Purpose |
|---|---|
| `index.html` | The entire app — HTML, CSS and JavaScript in one file |
| `manifest.json`, `service-worker.js`, `icon-*.png` | Make it installable and available offline |

**Built with:** vanilla HTML / CSS / JavaScript · `localStorage` · a service worker · [Supabase](https://supabase.com) (Auth, Postgres, RLS) · [Groq](https://groq.com) (optional)

---

## 🙏 Credits & attribution

Titles, covers and metadata come from third-party services, each with its own terms:

- [TMDB](https://www.themoviedb.org) — movies & TV. *This product uses the TMDB API but is not endorsed or certified by TMDB.*
- [AniList](https://anilist.co) — anime & manga
- [Jikan](https://jikan.moe) — unofficial MyAnimeList API
- [RAWG](https://rawg.io) — games
- iTunes Search API — music

All titles, artwork and trademarks belong to their respective owners.

---

<div align="center">

Made by [@Akshat-Neeraj](https://github.com/Akshat-Neeraj)

© 2026 Akshat Neeraj · All rights reserved

</div>
