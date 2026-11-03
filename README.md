# Friends of Bishop's Park — static site (Netlify-ready)

A fully static rebuild of friendsofbishopspark.com — no WordPress required.
Pulled from the live site's current content (via the WordPress REST API) on
9 July 2026, so this matches what's live now, including the new
Litterpicking photo and gallery/caption updates.

## Structure

```
index.html                        Homepage
news/index.html                   News
join-us/index.html                Join Us
nature-at-bishops-park/index.html Helping Nature
book/index.html                   Books & Cards
history/index.html                History
newsletter-archive/index.html     Newsletters & Archive
the-park-in-pictures/index.html   Gallery (50 photos, incl. Litterpicking)
privacy-policy/index.html         Privacy Policy (restyled to match the site)
constitution-and-rules/index.html Constitution & Rules (restyled to match the site)
404.html                          Custom not-found page
css/style.css                     Shared stylesheet (design system, no WordPress hacks)
images/                           All photos & illustrations, self-hosted
files/                            Membership form, AGM minutes, newsletters (self-hosted)
netlify.toml                      Netlify build/header config
```

Every page uses the `folder/index.html` convention, so clean URLs like
`/join-us/` and `/the-park-in-pictures/` work automatically on Netlify with
no extra redirect rules needed.

## Deploying to Netlify

**Fastest — drag and drop:**
1. Go to [app.netlify.com/drop](https://app.netlify.com/drop).
2. Drag this whole folder in. Done — you'll get a live URL immediately.

**Recommended — connect a Git repo (for future updates):**
1. Push this folder to a new GitHub repo.
2. In Netlify: Add new site → Import an existing project → pick the repo.
3. Build command: leave blank. Publish directory: `.` (repo root).
4. Deploy. Add your custom domain (friendsofbishopspark.com) under
   Site settings → Domain management once you're ready to cut over from
   WordPress.

## What's self-contained vs. still external

- **All images and illustrations** are downloaded and served locally from
  `/images/` — nothing depends on WordPress staying online.
- **Downloadable documents** (membership form, AGM minutes, newsletters,
  the reinstatement plan PDF) are downloaded and served locally from
  `/files/`.
- **External links are untouched** — things like the Stripe membership
  payment link, RSPB/Butterfly Conservation/iNaturalist links, the Google
  nature map, the Tea House and Fulham Society links, and the one Mailchimp
  newsletter archive link all still point to their original external sites,
  since those aren't part of this site.

## Notes

- The CSS is the same design system used on the WordPress site, with the
  WordPress/Twenty-Twenty theme override hacks stripped out (they're not
  needed outside WordPress).
- The Privacy Policy and Constitution & Rules pages were originally plain,
  unstyled WordPress content — they've been re-laid-out here using the same
  nav/header/footer and typography as the rest of the site, with no wording
  changes.
- If you add new pages or photos later, follow the same pattern: a
  `folder/index.html` file, images in `/images/`, and a stylesheet link to
  `/css/style.css`.
