# Whisper Challenge — Marketing Site

SEO-focused marketing site for **Whisper Challenge** (landing, privacy, terms).

## Stack

- [Astro](https://astro.build) (static)
- `@astrojs/sitemap`
- Brand assets from the Flutter app

## Pages

| Path | Purpose |
| --- | --- |
| `/` | Product landing (hero, how it works, modes, CTA) |
| `/privacy` | Privacy Policy |
| `/terms` | Terms of Use |

## Configure

Edit `src/config/site.ts`:

- `url` — currently `https://whisper.makduman.com`
- `supportEmail` — currently `support@makduman.com`
- `appStoreUrl` / `playStoreUrl`
- `legalEntity`

App links for Flutter (`lib/core/constants/app_links.dart`):

- Privacy: `https://whisper.makduman.com/privacy`
- Terms: `https://whisper.makduman.com/terms`
- Support: `support@makduman.com`

## Develop

```bash
npm install
npm run dev
```

## Build

```bash
npm run build
npm run preview
```

## Deploy (Vercel)

Static Astro build → `dist/`. Config: `vercel.json`.

```bash
npx vercel login
npx vercel          # preview
npx vercel --prod   # production
```

Or import the Git repo in the [Vercel dashboard](https://vercel.com/new) (Astro is auto-detected).

### Custom domain: `whisper.makduman.com`

1. Vercel → Project → **Settings → Domains** → add `whisper.makduman.com`
2. DNS (`makduman.com` zone):

| Type | Name | Value |
| --- | --- | --- |
| CNAME | `whisper` | `cname.vercel-dns.com` |

After DNS propagates:

- `https://whisper.makduman.com/privacy`
- `https://whisper.makduman.com/terms`
