# Mixpanel VIP — Digital Experience

Single-file mobile web app for the Tel Aviv VIP event. Scan a QR → personal event hub.

## Deploy to Render (Static Site)

1. Push this repo to GitHub (or your peer's GitHub account).
2. Go to [render.com](https://render.com) → **New** → **Static Site**.
3. Connect the GitHub repo.
4. Settings:
   - **Build command:** *(leave empty)*
   - **Publish directory:** `.`
5. Click **Create Static Site**. Done — Render gives you a `*.onrender.com` URL in ~30 seconds.

## Before going live — edit `CONFIG` in `index.html`

| Placeholder | What to replace with |
|---|---|
| `#REPLACE_SE_BOOKING_LINK` | Real SE Calendly / booking URL |
| `#REPLACE_AE_BOOKING_LINK` | Real AE Calendly / booking URL |
| `#REPLACE_VIDEO_*` | Hosted video URLs (YouTube / Loom / Vimeo) |
| Happening content | Real venue stations, food, swag |

## Loom demo embed

The "AI in action" tile opens the Mixpanel Agent Hebrew demo in a modal.
No config needed — already wired in.

## Production Mixpanel tracking

Find this line in the script and replace the stub:
```js
// === In production this is: mixpanel.track(event, payload) ===
```
Wire in your project token:
```js
mixpanel.init('YOUR_TOKEN');
mixpanel.track(event, payload);
```
