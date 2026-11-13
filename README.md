# server

Static site on GitHub Pages with two jobs:

1. `server-url.json` is the **pointer**: the phone app overwrites it with the current Cloudflare tunnel URL every time the tunnel changes.
   `{ "server_url": "https://xxxx.trycloudflare.com", "updated_at": "...", "status": "online" }`
2. `index.html` is a **chat page** for the language model running on the phone. It reads the pointer, then talks to `<server_url>/v1/chat/completions`.
   It streams replies, shows the model's thinking, and accepts pictures (shrunk to 768 px in the browser before sending).

Live: https://aquibahmed21.github.io/server/

Other apps should read `server-url.json` the same way; see the VPS Host project for the shared helper.
