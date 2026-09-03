# Taxes & Notary — Trainee Landing Pages

One page, unlimited trainee links. `yoursite.com/KeishaHobbs` and
`yoursite.com/JohnDoe` both load the same `index.html`, but each
trainee's name, logo, brand color, and contact email swap in
automatically based on the URL. Every page still carries a
"Backed by Taxes & Notary by Sherry" strip at the top, so your
company's experience stands behind them.

## Files

- `index.html` — the shared landing page (edit this once to change layout/copy for everyone)
- `trainees.json` — the roster (edit this to add/remove/rename trainees, set their logo and colors)
- `logos/` — put each trainee's logo image file in here
- `netlify.toml` — routing config, only needed if hosting on Netlify
- `vercel.json` — routing config, only needed if hosting on Vercel

## Adding a new trainee

1. Drop their logo file into `logos/` (e.g. `logos/alicia-keys.png`)
2. Open `trainees.json` and add an entry:

```json
"AliciaKeys": {
  "name": "Alicia Keys",
  "businessName": "Alicia Keys Tax Services",
  "email": "alicia@example.com",
  "tagline": "Where Ambition Meets Strategy",
  "logoUrl": "/logos/alicia-keys.png",
  "primaryColor": "#2f9e6e",
  "primaryDark": "#1f6e4a",
  "primarySoft": "#5cc294",
  "primaryLight": "#eafaf2",
  "backedBy": true
}
```

The key ("AliciaKeys") becomes the URL: `yoursite.com/AliciaKeys`.
Use no spaces or symbols in the key.

### Field reference

| Field | Required? | What it does |
|---|---|---|
| `name` | yes | Used for "Why [First Name]" text on the page |
| `businessName` | no | Their business name shown in the logo/title. Defaults to "[Name] Tax Services" if left out |
| `email` | no | Where the "Start My Tax Return" button sends inquiries |
| `tagline` | no | Small text under the logo. Defaults to "Where Ambition Meets Strategy" |
| `logoUrl` | no | Path to their logo image. Leave `""` to just show their business name as text instead |
| `primaryColor` / `primaryDark` / `primarySoft` / `primaryLight` | no | Their brand colors, replacing the pink theme. Leave `""` or omit to keep the default pink |
| `backedBy` | no | Set to `false` to hide the "Backed by Taxes & Notary by Sherry" strip for that trainee. Defaults to shown |

Save, commit/push (or drag-and-drop redeploy), and the new link is live.

## Deploying on Netlify

1. Push this folder to a GitHub repo (or drag-and-drop the folder into
   Netlify's dashboard for a one-off deploy).
2. In Netlify, "Add new site" → connect the repo → deploy.
   The `netlify.toml` file handles routing automatically, no build
   settings needed since this is plain HTML.
3. Point your custom domain (e.g. taxesandnotarybysherry.com) at the
   Netlify site in Site settings → Domain management.

## Deploying on Vercel

1. Push this folder to a GitHub repo.
2. In Vercel, "Add New Project" → import the repo → deploy.
   The `vercel.json` file handles routing automatically.
3. Point your custom domain at the Vercel project in Project settings → Domains.

## Notes

- Root URL (`yoursite.com` with no name) shows your own default page —
  the one still branded "Taxes & Notary by Sherry".
- A link with a name not in `trainees.json` shows a friendly "page not
  found" message rather than someone else's info by accident.
- The placeholder entries in `trainees.json` use example colors and
  emails — replace them with each trainee's real info before sending
  out their link.
