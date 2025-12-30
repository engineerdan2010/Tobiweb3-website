# Tobiofweb3 — Hero / Landing Demo

This is a small static demo for a bold Web3-style hero and landing page for `tobiofweb3`.

Files:
- `index.html` — the demo page (hero, about, projects, feed, CTA)
- `tobiofweb3.css` — dark neon styles used by the page
- `script.js` — a small mock feed renderer (replaceable with a live X/Twitter embed)

How to run:
1. Open `index.html` in your browser (double-click or via local server).

Replace mock feed with live X/Twitter posts:
- Option A (embed): Add X/Twitter embed code where `#feedGrid` is and remove `script.js` rendering.
- Option B (API): Use X API or a server-side proxy to fetch posts and render them into `#feedGrid`.

Styling notes & suggestions:
- Uses `Orbitron` for hero headlines and `Inter` for body text.
- Colors: neon gradients, dark backgrounds, glitch-like accents.

Next steps I can do for you:
- Add real X/Twitter widget code or connect to the API.
- Add wallet/ENS link integration and a small ENS lookup widget.
- Generate alt avatars / pixel art with SVGs or animated background.

Server (subscribe endpoint)
----------------------------
I added a simple Node.js server `server.js` exposing `POST /subscribe` which appends signups to `subscriptions.jsonl`.

How to run the server locally:

1. Open a terminal in the project folder:

```powershell
cd 'C:\Users\opopoola\Desktop\Tobiofweb3'
npm install
npm start
```

2. Open the site at http://localhost:3000 if you serve `index.html` via a static server, or run the site with a static file server and the API together (the API runs on port 3000 by default).

Notes on SMTP notifications (optional):
- To enable email notifications when a user signs up, set these environment variables before starting the server:

```powershell
#$env:SMTP_HOST = 'smtp.example.com'; $env:SMTP_PORT = '587'; $env:SMTP_USER = 'user'; $env:SMTP_PASS = 'pass'; $env:OWNER_EMAIL = 'you@example.com'; npm start
```

The server will attempt a best-effort notification if `SMTP_HOST` is present.

Security & next steps:
- This demo writes raw subscription lines to `subscriptions.jsonl` — for production, use a database and protect your endpoints.
- Add rate-limiting, captcha, and server-side validation for production usage.

