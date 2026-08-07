# Mollema Tech website

Statische site voor **[mollematech.nl](https://mollematech.nl)** (GitHub Pages).

## Pagina’s

| Bestand | URL (na DNS) | Doel |
|---------|--------------|------|
| `index.html` | https://mollematech.nl/ | Mollema Tech homepage |
| `urenbaas.html` | https://mollematech.nl/urenbaas.html | App-pagina (OAuth homepage) |
| `privacy.html` | https://mollematech.nl/privacy.html | Privacybeleid (OAuth + Play) |

## Lokaal bekijken

Open `website/index.html` in de browser, of serveer de map:

```bash
npx --yes serve website
```

## Deploy (GitHub Pages)

Workflow: `.github/workflows/deploy-website.yml` publiceert de map `website/` bij push naar `main`/`master`.

### DNS (domeinprovider)

Voor apex-domein `mollematech.nl` bij GitHub Pages typisch:

- **A**-records naar GitHub Pages IPs, of
- **CNAME** `www` → `jouw-user.github.io` + redirect

In de GitHub-repo: **Settings → Pages → Custom domain** → `mollematech.nl` → HTTPS aanzetten.

### Google OAuth / Play

1. Consent screen: Application home page = `https://mollematech.nl/urenbaas.html`
2. Privacy policy = `https://mollematech.nl/privacy.html`
3. Authorized domain = `mollematech.nl`
4. Play Console → Privacybeleid-URL hetzelfde
