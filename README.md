# planetar-site

The public project page served at **https://planetar.ca** and **https://www.planetar.ca**.
It's a static page (`index.html`, `style.css`, `favicon.svg`) with no build step.

The live demos run on subdomains:

- **https://vic.planetar.ca** runs `planetar-ui`, the analyst workspace on live Victoria AIS (it moved from the apex on 2026-10-31).
- **https://orca.planetar.ca** will run `planetar-ui-orca` (in development).

## Preview

```
python3 -m http.server 7090 --bind 127.0.0.1
```

## Deploy (www0)

nginx serves this directory statically; see `deploy/planetar.nginx` and
`~/data/vaults/docs/DEPLOY-planetar.md`. To update: `git fetch origin main && git reset --hard origin/main`
in `/Users/sness/github/planetarx/planetar-site` on www0. No reload is needed.

The apex server block still proxies `/ws` and `/api/` to the bridge and ontology. Two clients depend on that:
the Flutter app (defaults to `wss://planetar.ca/ws`) and the URLs cited in the filed CH13/CH14 bids.

License: GPL-3.0-or-later.
