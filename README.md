# CRM Health Check

A free, ~1-minute self-assessment that gives a small-business owner a **CRM health score (0–100)**
plus the top fixes worth making — and ends with an option to book a free 30-minute audit.

- **`index.html`** — the whole thing. One self-contained file: inline CSS + JS, **no backend, no
  build step, no dependencies, no data leaves the browser.** 8 weighted questions across data
  hygiene, pipeline, automation, reporting, adoption, ownership, integrations and value. The
  "first things I'd fix" list is personalized from the respondent's weakest answers.

There's no email-capture form on purpose — the calendar booking *is* the lead capture, so there's
nothing to host or wire up.

## Editing

- **Booking link:** change `BOOKING_URL` at the top of the `<script>`.
- **Questions / fixes:** edit the `QUESTIONS` array — each item is `{cat, q, fix}`, scored 0/1/2.
- **Wording, colors:** all inline; the `:root` CSS variables hold the palette.

## Publishing

Any static host works — this repo serves via GitHub Pages at
[isequeira251.github.io/crm-health-check](https://isequeira251.github.io/crm-health-check/).
You can also open `index.html` locally to preview.

---

Part of [isequeira251.github.io](https://isequeira251.github.io/) — Ian Sequeira, fractional
HubSpot & RevOps for sales-led teams.
