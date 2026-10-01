# Dhana Kolam Workshop — landing page

Self-contained, mobile-first page. Open `index.html` in a browser to preview. No build step.

## Files
- `index.html` — the landing page (Tanglish copy, illustrations, drill calculator, checkout modal)
- `thank-you.html` — post-payment page. Fires the Meta **Purchase** event here, not on the button click.
- `images/makkal.jpg` — Vishnu on Makkal TV (copied from financemantiri.com, 682×409). Used in the Guide section. Confirm Makkal TV is fine with the screenshot and logo being used on the page, and swap in a higher-resolution copy if you have one.
- `images/video-poster.jpg` — optional 16:9 poster for the video box. The page falls back to a placeholder if it is missing.
- Open `index.html` directly in a browser (or deploy it) to see the images. Some preview panes can't load local image files.

## Fill in (top of the `<script>` in index.html)
| Setting | What to put |
|---|---|
| `DRAFT_MODE` | `true` shows yellow CONFIRM chips and a banner. Set `false` only when every claim is confirmed. |
| `PIXEL_ID` | Meta Pixel ID (same value in `thank-you.html`) |
| `PAYMENT_URL` | Cashfree payment link. Set its return URL to `thank-you.html`, and only after a **successful** payment. |
| `SHEET_WEBHOOK` | Google Apps Script web app URL for lead backup (name, WhatsApp, email). Run it once and click through the consent screen before testing. |
| `VIDEO_URL` | A YouTube/Vimeo **embed** URL (for example `https://www.youtube.com/embed/ID`) |
| `WORKSHOP` | date, time, format, language, duration, seats |
| `SHOW_SEATS` | `true` only if the seat count is real |
| `SHOW_PROOF` | `true` only when real, permissioned testimonials replace the slots |
| `SHOW_MEDIA_LOGOS` | `true` only after Vishnu confirms permission |

`thank-you.html` has its own `CONFIG`: `PIXEL_ID`, `WHATSAPP_GROUP`.

## Meta events
PageView (load) · ViewContent (50% scroll) · InitiateCheckout (any CTA click) · Lead (form submit) · Purchase (thank-you page only).

## Before launch
- [ ] Native Tamil read-through of every line
- [ ] Resolve every CONFIRM chip, then set `DRAFT_MODE` to false
- [ ] Remove `<meta name="robots" content="noindex">` when ready to be indexed
- [ ] Add real Terms, Privacy, Refund and Contact pages and link them in the footer and form
- [ ] Test the payment flow end to end, including the return to `thank-you.html`
- [ ] Check IRDAI advertising rules
- [ ] Never reuse the old date (5 Sep 2026), the ₹73 price or the 100-seat claim
