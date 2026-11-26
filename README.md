# Live web clock

`index.html` is the whole thing: one static page that connects to the EMQX broker over a secure websocket
(port 8084, path /mqtt), listens to `weasley/sahil` and `weasley/gargi` (plus their `/info` detail), and moves the hands live.

- **Login:** it uses the read-only EMQX user `viewer`, which may only subscribe to `weasley/#`.
  The username and password go in the link after `#`, e.g. `.../#u=viewer&p=PASSWORD`. The part after `#` never leaves the phone, so it is not in the page or in any server log.
- **Needs the brain running** on the laptop; the page only shows what the brain publishes.
- **To change the page:** edit `index.html` and push it to the GitHub Pages repo again.
