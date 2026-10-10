# AerOps — Static Website

Single-file static site for aerops.space. No build step, no backend.

## Deploy

Open `index.html` locally, or drop it on any static host:
- Netlify / Vercel / Cloudflare Pages / GitHub Pages

## Edit

All copy, team members, status badges, and contact email live in the `CONFIG` object at the bottom of `index.html` inside the `<script>` block.

### Placeholders to replace
1. `CONFIG.email` — your final business email
2. `CONFIG.team` — add/remove team members
3. `CONFIG.solutions[*].capabilities[*].status` — promote CONCEPT → PROTOTYPE → LIVE as they ship
4. `CONFIG.updatedDate` — update when privacy policy changes
5. Privacy policy — review with counsel before relying on it
