# block-puzzle-legal

The Privacy Policy and Terms of Service for **Block Puzzle Color Blast**
(`fudge.block.puzzle.colorblast`), an Android puzzle game by Golden Garuda Studios.
Published as a static site with GitHub Pages.

Google Play requires a reachable Privacy Policy URL on the store listing, so this repo
is a **production dependency of the shipped app**, not documentation.

## Live URLs

    https://ggaruda-studios.github.io/block-puzzle-legal/
    https://ggaruda-studios.github.io/block-puzzle-legal/privacy
    https://ggaruda-studios.github.io/block-puzzle-legal/terms

## Publishing

1. Push these files to the default branch of `GGaruda-Studios/block-puzzle-legal`.
2. **Settings → Pages → Source: Deploy from a branch → `main` / `/ (root)`.**
3. Wait for the first build, then open all three URLs above in a browser.

A Privacy Policy URL that 404s is worse than a missing one: Play rejects the listing.

## Do not rename these paths

The Play listing points at `/privacy`. If the app ever links to these pages from its
Settings screen, every released build carries the URL baked in, and renaming a folder,
the repo or the org breaks the links in installed apps. If a path has to change, leave
a redirect at the old one.

Pages are `privacy/index.html` and `terms/index.html` so the extensionless URLs work on
any static host.

## No webfonts, analytics or trackers

Deliberate. Every page is plain HTML plus one local stylesheet, so reading the policy
cannot be logged by anyone but GitHub. `.nojekyll` makes GitHub Pages serve the files
as written.

## Updating a document

1. Edit the HTML.
2. Change the `Last updated` date **and** the `datetime` attribute next to it.
3. If a change is material, say so in the app's Play release notes.

The app currently has no internet permission and collects nothing. **Adding ads,
analytics or any network feature means updating the Privacy Policy before that version
is released**, changing the Play Data safety answers with it, and adding a
`delete-data/` page like the one in `tricky-arrows-legal`.
