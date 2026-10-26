# block-puzzle-legal

The Privacy Policy, Terms of Service and data-deletion page for **Block Puzzle Color Blast**
(`fudge.block.puzzle.colorblast`), an Android puzzle game by Golden Garuda Studios.
Published as a static site with GitHub Pages.

Google Play requires a reachable Privacy Policy URL on the store listing, so this repo
is a **production dependency of the shipped app**, not documentation.

## Live URLs

    https://ggaruda-studios.github.io/block-puzzle-legal/
    https://ggaruda-studios.github.io/block-puzzle-legal/privacy
    https://ggaruda-studios.github.io/block-puzzle-legal/terms
    https://ggaruda-studios.github.io/block-puzzle-legal/delete-data

## Publishing

1. Push these files to the default branch of `GGaruda-Studios/block-puzzle-legal`.
2. **Settings → Pages → Source: Deploy from a branch → `main` / `/ (root)`.**
3. Wait for the first build, then open all four URLs above in a browser.

A Privacy Policy URL that 404s is worse than a missing one: Play rejects the listing.

## Do not rename these paths

The Play listing points at `/privacy` (and the Data safety form at `/delete-data`). If the
app ever links to these pages, every released build carries the URL baked in, and renaming
a folder, the repo or the org breaks the links in installed apps. If a path has to change,
leave a redirect at the old one.

Pages are `privacy/index.html`, `terms/index.html` and `delete-data/index.html` so the
extensionless URLs work on any static host.

## No webfonts, analytics or trackers

Deliberate. Every page is plain HTML plus one local stylesheet, so reading the policy
cannot be logged by anyone but GitHub. `.nojekyll` makes GitHub Pages serve the files
as written.

## The app carries copies

Settings → Privacy & Terms inside the game shows the same two documents as text
(`scripts/legal_catalog.gd` in the game repo), so reading them there sends nothing.
**Change a document here and in that file together**, and bump the date in both.

## Updating a document

1. Edit the HTML.
2. Change the `Last updated` date **and** the `datetime` attribute next to it.
3. Make the same change in the game's `scripts/legal_catalog.gd`.
4. If a change is material, say so in the app's Play release notes.

## What the app does today

The app sends **anonymous usage data (Firebase Analytics) and crash reports (Firebase
Crashlytics)**, and optionally posts scores and achievements to Google Play Games. In the
EEA, UK and Switzerland (and where the device region is unknown) Firebase collection is off
until the player switches on **Settings → Privacy & Terms → Share usage data**; elsewhere it
is on. Advertising consent is always denied. Retention: analytics 14 months, crashes
90 days (set in the Firebase project).

Adding ads, other SDKs or any new kind of data means updating the Privacy Policy before that
version is released, and changing the Play Data safety answers with it.
