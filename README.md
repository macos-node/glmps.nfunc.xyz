# glmps.nfunc.xyz

> Public Nostr discography — releases as kind:31237 events.

**Live**: <https://glmps.nfunc.xyz>

## Stack

- [Vite](https://vitejs.dev/) + React 18 + TypeScript
- Tailwind CSS
- [nostr-tools](https://github.com/nbd-wtf/nostr-tools)
- lucide-react

## Nostr

- **Login**: NIP-07 (browser extension) + NIP-55 (Amber callback URI)
- `kind:31237` — release event
- `kind:7` — reactions
- `kind:0` — profile lookup

Owner = `nurture@fizx.uk` (`OWNER_NPUB` in `src/config.ts`). Owner-only publish; any signed-in user can react. **nginx vhost needs SPA fallback** for `/r/<naddr>` deep links.

## Develop

```bash
npm install
npm run dev
```

## Build + deploy

```bash
./deploy.sh
```

Builds, rsyncs `dist/` to the deploy host and checks the live site serves the
new build.

> The nginx vhost for this site uses an SPA fallback:
> `location / { try_files $uri $uri/ /index.html; }`
> so client-side routes resolve. A reference copy is in
> `nginx-glmps.nfunc.xyz.conf`.

## The three forks

glmps is published three times from three repos that differ only in a handful
of per-site files: the coral one, the emerald one and this monochrome one.
All three carry all three themes; tapping the `glmps` wordmark cycles them.
This fork's default is `mono`.

---

_Sister repos: <https://github.com/macos-node/glmps.upleb.uk> · <https://github.com/adjmx/glmps.fizx.uk>_
