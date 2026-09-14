# akkomath2

MathLab 7→8 with a hidden unlock into embedded AkkoAudio.

## Repo
https://github.com/baobao739/akkomath2

## Unlock
1. Open the site
2. Go to **Quiz**
3. Submit the special answer **3 times** (looks like a wrong answer)
4. AkkoAudio loads

## Security (what we did)
- Secret is **never stored as plaintext** in the page (SHA-256 fingerprint only)
- Rate limit + progressive lockout in `localStorage`
- Session token after unlock
- No secret string searchable in source as `akko777`

### Honest limits
This is still **client-side** HTML. A determined person with DevTools can eventually reverse it.

Your real **akkoaudio** setup is stronger because codes are checked by **Netlify Functions** (server-side) and admin is password-gated via the server. That is the right model if you need real security.

## Deploy
1. Download the full hardened `index.html` from the chat
2. Replace this repo's `index.html` (GitHub → Add file → Upload files)
3. Or drag the file onto https://app.netlify.com/drop

## Related
- https://github.com/baobao739/akkoaudio (full player + server access codes)
- https://github.com/baobao739/akkomath (earlier math lab)
