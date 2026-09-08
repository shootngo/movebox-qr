# Stashr

Household storage inventory for attics, outbuildings, and cabinets. Print a QR label for a box, scan it to see what’s inside, or search for an item and get the exact box and location.

This is a personal, single-household tool. It is not a move tracker, not part of Nestor, and it does not require a login.

**Live:** https://shootngo.github.io/stashr/

## Offline / Add to Home Screen (Android)

1. Open https://shootngo.github.io/stashr/ in Chrome.
2. Menu → **Add to Home screen** / **Install app**.
3. Stashr uses its own name, icon, theme colors, and service-worker cache (`stashr-v1`), so it will not collide with Nickey or Rosa.
4. After the first online visit, scan, search, and the app shell work offline. Inventory lives in `localStorage`; box photos live in IndexedDB.
5. Chrome speech-to-text may still need a network hop to transcribe audio. The lookup itself and the spoken answer (`speechSynthesis`) are local — there is no Gemini/cloud search.

## Data

- **Boxes** get codes like `STASH-0001`, a name, a hierarchical location (area + optional cabinet code), notes, and an optional photo.
- **Items** live in a box or directly on a location, and can be marked **checked out** when pulled from storage.
- **Locations** start with household defaults (Craft Room Attic, Playroom Attic, Pole Barn Attic with A1–C10, Outbuildings, Garage, Workshop, and common closets). New areas and cabinet codes typed in the app are remembered.

Export/import JSON from the menu for backup. No Google Drive sync.

## Develop

This is a static GitHub Pages site (root of `main`). Serve locally with any static server, e.g. `python3 -m http.server 8080`.
