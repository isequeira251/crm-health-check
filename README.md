# CRM Health Check

A free, ~1-minute self-assessment that gives a small-business owner a **CRM health score (0–100)**
plus the top fixes worth making — and ends with a CTA to book a free 30-minute audit. It's the
**inbound** half of the consulting funnel: instead of chasing leads, prospects self-qualify (only
someone genuinely feeling the pain finishes it and books).

- **`index.html`** — the whole thing. One self-contained file: inline CSS + JS, **no backend, no
  build step, no dependencies, no data leaves the browser.** 8 weighted questions across data
  hygiene, pipeline, automation, reporting, adoption, ownership, integrations and value. The "first things I'd fix" list
  is personalized from the respondent's weakest answers, and each maps to a service offering.

## How it fits the funnel

It's the opposite motion from `crm-prospector` (which finds + reaches out). Here the prospect comes
to **you**: you share the link (LinkedIn posts/DMs, email signature, referral partners, the
first-touch DM from `main.py linkedin`), they get a score, and the booking link captures the lead.
No email-capture form on purpose — the calendar booking *is* the lead capture, so there's nothing to
host or wire up.

## Editing

- **Booking link:** change `BOOKING_URL` at the top of the `<script>` (currently the same Google
  Calendar link the SDR agent uses).
- **Questions / fixes:** edit the `QUESTIONS` array — each item is `{cat, q, fix}`, scored 0/1/2.
- **Wording, colors:** all inline; the `:root` CSS variables hold the palette.

## Publishing (free, ~2 min)

Any static host works. Easiest is GitHub Pages:

```bash
cd /home/ian/crm-health-check
git init && git add -A && git commit -m "CRM Health Check scorecard"
gh repo create crm-health-check --public --source=. --push
gh api -X POST repos/isequeira251/crm-health-check/pages -f 'source[branch]=main' -f 'source[path]=/'
# live at https://isequeira251.github.io/crm-health-check/ within a minute or two
```

Or drag the file onto Netlify Drop, or open `index.html` locally to preview first.
A custom domain (e.g. `crmhealthcheck.<yourdomain>`) reads more credibly once the consulting LLC has one.
