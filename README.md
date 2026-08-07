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

Repo: https://github.com/Mollema88/mollematech-website  
Pages is al gezet op custom domain `mollematech.nl` (CNAME-bestand aanwezig).

Bij je domeinprovider voor **mollematech.nl** (apex) deze **A**-records:

| Type | Naam | Waarde |
|------|------|--------|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |

Optioneel **www**:

| Type | Naam | Waarde |
|------|------|--------|
| CNAME | `www` | `Mollema88.github.io` |

Daarna in GitHub: **Settings → Pages** → wacht tot domain verified → **Enforce HTTPS** aanzetten.

Tijdelijk zonder DNS: de site draait ook via GitHub Pages Actions; zodra DNS live is: `https://mollematech.nl/`.

### Google OAuth / Play

1. Consent screen: Application home page = `https://mollematech.nl/urenbaas.html`
2. Privacy policy = `https://mollematech.nl/privacy.html`
3. Authorized domain = `mollematech.nl`
4. Play Console → Privacybeleid-URL hetzelfde
