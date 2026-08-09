# Ledger — Interest, Itemized

A single-page, single-file interest calculator styled like an open ledger book. Five calculators, a Thai/English language switch, and a "how it's calculated" popover for every result — all running client-side with zero dependencies and zero network calls.

---

## Features

- **Five calculators in one place**
  - Simple interest
  - Compound interest (annually / semi-annually / quarterly / monthly / daily)
  - Loan / EMI with a full yearly amortization table
  - Recurring deposit
  - Savings goal (reverse-solves for the monthly amount, or lump sum, needed to hit a target)
- **Thai / English language switch** — Thai by default, one tap flips every label, caption, unit, and table header
- **"How it's calculated" modals** — a small brass "?" button on every result opens a popover with the formula, a plain-language explanation, and a worked example using your actual numbers
- **Live inline charts** — bar splits, stacked growth charts, and a donut chart, all hand-drawn SVG (no charting library)
- **Count-up number animation** on every result
- **Currency picker** per calculator (USD, EUR, GBP, THB, INR, JPY, AUD, SGD)
- **Fully responsive**, down to small phones, with a scroll-hinted tab bar
- **Themed scrollbars**, custom range sliders, and a paper-textured "ledger" surface throughout

## Tech stack

Nothing to install. It's one HTML file:

- Vanilla HTML / CSS / JavaScript — no framework, no build step
- Google Fonts: [Fraunces](https://fonts.google.com/specimen/Fraunces) (display serif), [Noto Sans Thai](https://fonts.google.com/noto/specimen/Noto+Sans+Thai), [Inter](https://fonts.google.com/specimen/Inter), and [IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Mono) for tabular figures
- Hand-written SVG for every chart (bar splits, stacked growth, donut) — no Chart.js / D3
- All math (simple interest, compound interest, EMI, annuity future value, goal-seek) is implemented from scratch as plain JavaScript functions

## How it was built

This started as a straightforward "build an interest calculator" request and grew feature by feature through conversation:

1. **Concept & design direction** — picked a "ledger book" visual metaphor instead of a generic dashboard: a dark cover-green page, an open paper "book" as the main surface, brass accents, ruled lines like real ledger paper, and monospace tabular figures so numbers line up the way they do in an actual accounting book.
2. **Core calculators** — built simple interest, compound interest, loan EMI, recurring deposit, and savings goal as independent panels sharing one design system, each with linked sliders + number inputs and a live SVG chart.
3. **Internationalization** — added a Thai/English toggle (Thai as the default language), with every label, caption, chart legend, and table header driven from a single translation dictionary so nothing is hard-coded per language.
4. **Formula transparency** — added a "?" button on each result that opens a modal explaining the formula in plain language *and* plugs in the person's current numbers so they can see exactly how the total was reached.
5. **Polish pass** — iterated on spacing, mobile layout, color contrast between decorative and functional lines, and custom-styled scrollbars to keep the whole thing feeling considered rather than default.

## Project structure

```
.
├── index.html   # the entire app — HTML, CSS, and JS in one file
└── README.md
```

There's no build process. Open the HTML file in a browser, or serve the folder with any static host (GitHub Pages, Netlify, Vercel, etc.).

## Running it locally

```bash
git clone <your-repo-url>
cd <your-repo>
open interest-calculator.html   # or just double-click it
```

No `npm install`, no server required — it's a static file.

## Notes

- All calculations run entirely in the browser. Nothing is sent to a server, logged, or stored.
- Figures are estimates for general planning purposes, not financial advice.

## License

MIT — do whatever you'd like with it.
