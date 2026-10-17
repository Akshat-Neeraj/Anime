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

## 🛠 Run your own copy

<details>
<summary><b>1 · Host it (2 minutes, no build step)</b></summary>

Fork this repo, then **Settings → Pages → Deploy from a branch → `main` / root**. Your copy is live at `https://<you>.github.io/<repo>/`.
</details>

<details>
<summary><b>2 · Turn on accounts (optional)</b></summary>

1. Create a free project at [supabase.com](https://supabase.com).
2. **SQL Editor →** paste all of [`supabase-schema-accounts.sql`](supabase-schema-accounts.sql) **→ Run**. (Safe to re-run. A "destructive operation" warning is just the `DROP POLICY` lines — click *Run query*.)
3. **Authentication → URL Configuration:** set *Site URL* to your hosted URL and add it under *Redirect URLs*.
4. Open `index.html`, search for **`PUBLIC BUILD CONFIG`**, and paste your project URL and **anon public** key between the quotes.
5. Open your site, sign up, then make yourself admin in the SQL Editor:
   ```sql
   update profiles set is_admin = true
   where id = (select id from auth.users where email = 'you@example.com');
   ```
</details>

<details>
<summary><b>3 · Add Google sign-in (optional)</b></summary>

1. [Google Cloud Console](https://console.cloud.google.com) → **Credentials → Create OAuth client ID → Web application**.
2. *Authorised JavaScript origins:* `https://<you>.github.io` (no path, no trailing slash).
3. *Authorised redirect URIs:* `https://<your-project-ref>.supabase.co/auth/v1/callback`
4. Supabase → **Authentication → Providers → Google:** switch it **on**, paste the Client ID and Secret, **Save**.
</details>

<details>
<summary><b>4 · Use your own API keys</b></summary>

`SHARED_TMDB_KEY` in `index.html` is a shared fallback that can be rate-limited — replace it with your own free [TMDB](https://www.themoviedb.org/settings/api) key. Leave `HARDCODED_KEY` empty and let each user enter their Groq key in the app.
</details>

### ⚠️ Security notes for forks
- The Supabase **anon** key is *meant* to be public — it's safe **only because** the schema turns on Row Level Security. Never paste the **`service_role`** key into this repo.
- Don't commit a real Groq key.

---

## 📁 What's in the repo

| File | Purpose |
|---|---|
| `index.html` | The entire app — HTML, CSS and JavaScript in one file |
| `manifest.json`, `service-worker.js`, `icon-*.png` | Make it installable and available offline |
| `supabase-schema-accounts.sql` | Database tables + security rules for optional accounts |

**Built with:** vanilla HTML / CSS / JavaScript · `localStorage` · a service worker · [Supabase](https://supabase.com) (Auth, Postgres, RLS) · [Groq](https://groq.com) (optional)

---

## 🙏 Credits & attribution

Titles, covers and metadata come from third-party services, each with its own terms:

- [TMDB](https://www.themoviedb.org) — movies & TV. *This product uses the TMDB API but is not endorsed or certified by TMDB.*
- [AniList](https://anilist.co) — anime & manga
- [Jikan](https://jikan.moe) — unofficial MyAnimeList API
- [RAWG](https://rawg.io) — games
- iTunes Search API — music

All titles, artwork and trademarks belong to their respective owners. If you fork this to run a commercial service, read each provider's terms first — for example, TMDB's API is free for non-commercial use and needs a separate license for commercial use.

---

<div align="center">

Made by [@Akshat-Neeraj](https://github.com/Akshat-Neeraj)

</div>
