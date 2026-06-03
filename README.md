# Rinkal's Kitchen 🍛

**Home-cooked food at your fingertips — your neighbourhood kitchen.**

A mobile-first ordering site for a home cook serving fresh, 100% vegetarian Gujarati & Punjabi food to her local community. Customers browse the menu, build an order, and send it in one tap over WhatsApp — paying cash on pickup. No apps, no accounts, no card processing.

🔗 **Live site:** (https://gayatriswaminathan.github.io/cook-site/)

---

## Why this exists

The cook already takes orders by WhatsApp and gets paid in cash. The goal wasn't to replace that — it was to make it effortless and to turn one-off buyers into a community of regulars. The site meets customers where they already are (WhatsApp) instead of forcing a new checkout flow.

## Features

- **Tap-to-order cart** that composes a single, itemized WhatsApp message with a running total
- **Mobile-first, delivery-app layout** — compact rows, big tap targets, sticky order bar
- **Smart menu navigation** — sticky category tabs, a "Popular this week" row, and per-dish veg/spice indicators
- **Sized items** — sabjis in 8oz / 16oz with a toggle
- **Family meal packs** — bundled, anchor-priced combos (rice + sabji + curry + appetizer + sweets) to lift order size
- **Weekly tiffin plans** — recurring meal sign-up to build repeat customers
- **Community touches** — specials, neighbour reviews, WhatsApp community CTA
- **Gujarati design motifs** — toran, bandhani, and a block-print medallion, kept subtle
- **Conversion micro-interactions** — add-to-cart feedback, a pulsing order button, a scroll nudge (all respect `prefers-reduced-motion`)

## Product & design decisions

- **WhatsApp + cash, by design.** The cook's real workflow is WhatsApp and cash, so the product amplifies it rather than replacing it — lower friction, zero payment fees.
- **Appetizers lead the menu.** They have the strongest photography, so they hook the visitor before they scroll.
- **Anchor-priced family packs.** A clearly-badged "Most popular" mid tier and a "Best value" large pack steer demand toward higher-margin bundles.
- **Everything in one editable config block.** Menu, prices, specials, reviews, and contact live at the top of `index.html` so the owner can update them without touching layout code.

## Tech

- Single self-contained `index.html` — HTML, CSS, and vanilla JavaScript, no build step and no framework
- Google Fonts (Inter) for type; all other assets are local
- Dish photos in `/photos`
- Hosted free on **GitHub Pages**

## Run locally

Just open `index.html` in a browser — there's nothing to install or build.

## Project structure

```
cook-site/
├── index.html      # the entire site (markup, styles, logic, menu data)
├── photos/         # dish photography
└── README.md
```
