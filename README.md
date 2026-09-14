# akkomath2

MathLab 7→8 (Pre-Algebra → Algebra 1) with a hidden unlock into the embedded AkkoAudio player.

## How to unlock
1. Open the site
2. Switch to **Quiz** mode
3. Submit the special answer **3 times** (it still looks like a wrong answer)
4. AkkoAudio loads in-place

## Security notes (important)

This is a **static client-side** page. That means:

- The unlock secret is **never stored as plaintext** (only a SHA-256 fingerprint is checked).
- Attempts are **rate-limited / locked out** in `localStorage`.
- A short **session token** is written after a successful unlock.

**However:** anything that runs only in the browser can eventually be reverse-engineered by a determined person with DevTools.  
For production-grade access control (like the main [akkoaudio](https://github.com/baobao739/akkoaudio) repo), keep using **Netlify Functions** + server-side codes + the admin panel.

## Deploy
Drag this repo (or just `index.html`) onto [Netlify Drop](https://app.netlify.com/drop), or connect the GitHub repo to Netlify.

## Files
- `index.html` — full MathLab + embedded AkkoAudio + hardened unlock gate
