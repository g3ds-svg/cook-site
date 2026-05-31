# Project Notes — Rinkal's Kitchen (context for resuming)

> Read this + `STRATEGY.md` to restore full context in a new session.

## What this is
A mobile-first ordering site for Rinkal, a home cook serving 100% vegetarian Gujarati & Punjabi food. Customers build an order and send it via WhatsApp; she's paid in cash on pickup. Built AI-accelerated as a 0→1 product + portfolio piece (owner: Gayatri Swaminathan, Senior TPM).

## Status
- **Live:** https://g3ds-svg.github.io/cook-site/
- **Repo:** https://github.com/g3ds-svg/cook-site (GitHub Pages, main branch, root)
- **Local folder:** AI Projects/cook-site (`index.html`, `photos/`, `README.md`, `STRATEGY.md`, this file)
- Push flow: `git add . && git commit -m "..." && git push`

## Architecture
- Single static `index.html` — HTML/CSS/vanilla JS, no build step, no backend.
- All content (menu, prices, specials, reviews, contact) lives in one editable `CONFIG`/`MENU` block at the top of the file.
- Ordering hands off to WhatsApp via `wa.me` link (no server = no order DB yet).
- Dish photos in `/photos`, sliced from the owner's two menu-grid images.

## Key decisions made
- Design direction: **Clean Light Sans** (white, Inter, one spice-red accent, minimal).
- **Appetizers shown first** (strongest photos = the hook).
- **Family meal packs** with anchor pricing ("Most popular" mid tier, "Best value" large pack).
- **Weekly tiffin** tiers (Mini/Family) as WhatsApp sign-ups.
- Subtle **Gujarati motifs**: toran, bandhani, block-print medallion.
- **Dopamine micro-interactions**: fly-to-cart, count bump, mobile haptics, confetti on first add; pulsing order button; popular-row nudge. All respect reduced-motion.
- Order WhatsApp message reformatted to be clean/scannable (header, one item per line, dividers, bold total, name/pickup prompts).
- Pickup only (no delivery). Address removed for privacy.

## OPEN ITEMS / TODO
- [ ] **WhatsApp number** is still placeholder `10000000000` — replace to go order-ready.
- [ ] **Dal Makhani price** discrepancy: owner's grid showed $6, but sabjis are 8oz $10 / 16oz $13 — confirm.
- [ ] **Sabji curry photos** missing (paneer gravies, aloo gobi, bhindi, baingan, channa, kadhi, kofta) — need a 3rd menu-grid image to slice.
- [ ] **Combo & tiffin prices** are my suggestions — confirm real numbers (rice & sweet-box prices unknown).
- [ ] **Latest changes not yet pushed** (clean order message + dopamine animations).
- [ ] **Custom domain** (e.g., rinkalskitchen.com) for marketing instead of the github.io URL.
- [x] **Observability Tier 0 ADDED** — `OBS` config block + `track()` event layer in index.html. Funnel events: page_view, add_to_cart, remove_from_cart, order_submit (carries full cart payload), combo_order, tiffin_interest, join_community, js_error. GA4 + Sentry behind config placeholders; `debug:true` logs events to the browser console now.
  - [ ] To activate: set `OBS.ga4Id` (GA4) and `OBS.sentryDsn` (Sentry).
  - [ ] **Tier 1** (serverless backend + orders DB + owner dashboard): set `OBS.endpoint` to your events API — `order_submit` already sends the structured cart, so it's a drop-in. Also add a CI/CD deploy for the backend.
- [x] **CI/CD pipeline ADDED** — `.github/workflows/deploy.yml` (verify → deploy to Pages). Pages source set to GitHub Actions.

## Business direction
See `STRATEGY.md` — staged path from one cook → productized template → neighborhood beachhead → multi-cook, multi-cuisine marketplace. Watch cottage-food-law constraints before centralizing payments.
