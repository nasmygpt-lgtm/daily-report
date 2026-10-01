# Daily Travel Agency Visit Report Generator

A clean, responsive, single-page web tool that helps a hotel sales manager turn
raw daily visit notes into a polished, email-ready report.

**No build step, no server, no dependencies** — it's a single `index.html` file
that runs entirely in your browser. Nothing is uploaded.

## Features

- **Two input modes**
  - **Paste Raw Notes** — dump unstructured notes for multiple agencies at once.
    Separate agencies with a blank line; the first line (or `Agency: Name`)
    becomes the name. `Agency Name – notes` on a single line also works.
  - **Structured Fields** — enter one agency at a time with dedicated
    **Agency Name**, **Meeting Notes**, and optional **Rates / Inquiry Details**
    fields, then build a list.
- **Automatic formatting** — every entry is rendered as
  `**Agency Name** – cleaned text` (bold name, em-dash, tidied notes).
- **Light spelling & grammar cleanup** — fixes common typos
  (`intrested → interested`, `follwup → follow-up`, `enquiry → inquiry`,
  `nxt → next`, …), normalizes spacing and capitalization, and adds terminal
  punctuation.
- **Technical data is preserved exactly** — the cleanup never touches digits,
  so pax counts, dates, room counts, and prices (e.g.
  `INR 6200/room/night, 30 rooms, 3 nights`, `USD 1,250.50`) pass through
  byte-for-byte.
- **One-click copy**
  - **Copy (formatted)** — rich HTML, so bold names paste straight into
    Gmail / Outlook / Slack.
  - **Copy as Markdown** — plain `**Name** – text` for Markdown-aware chat.
- **Live preview** as you type (bulk mode), an agency counter, per-entry
  removal, a *Load example* button, and a fully responsive layout.

## Usage

1. Open `index.html` in any modern browser (double-click it, or drag it into a
   browser tab).
2. Click **Load example** to see it in action, or paste your own notes.
3. Click **Generate Report**, then **Copy (formatted)** and paste into your
   email or chat.

### Example

Input:

```
Sunrise Travels
met with ravi, intrested in group booking for 25 pax arriving 12 nov, needs 12 rooms, quoted INR 4500 per night

Horizon Holidays - casual visit, no new leads but they wil revert nxt wk
```

Output:

> **Sunrise Travels** – Met with ravi, interested in group booking for 25 pax arriving 12 nov, needs 12 rooms, quoted INR 4500 per night.
>
> **Horizon Holidays** – Casual visit, no new leads but they will revert next week.

## License

MIT
