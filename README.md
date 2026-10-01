# Daily Travel Agency Visit Report Generator

A clean, responsive, single-page web tool that helps a hotel sales manager turn
raw daily visit notes into a polished, email-ready report.

**No build step, no server, no dependencies** — it's a single `index.html` file
that runs entirely in your browser. Nothing is uploaded.

It is tuned to the sales manager's existing **house report style**:

> **Agency Name** – Visited and met … / Discussed with … (narrative, with
> rates, pax, dates and room counts embedded exactly as written).

## Features

- **Two input modes**
  - **Paste Raw Notes** — dump a whole day of notes at once. Write each agency
    as `Agency Name – notes` and separate agencies with a blank line. Multi-line
    pax / room / rate blocks under an agency (e.g. `10-23 Nov` / `5 pax` /
    `2 Room + 1 extra bed`) are kept together in one entry. `Agency: Name` and a
    plain agency name on the first line also work.
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
Dahr – Visited and met Director of Sales. special rates has been offered AED 220/240 and requested to push for all market this rates.

Arabian Journey – Discussed with group incharge
10-23 Nov
5 pax
2 Room + 1 extra bed
offered AED 275+15 with meal charges.

Al Hadaf – Disscussed with Sales, rates given 250+15 for Oct.
```

Output:

> **Dahr** – Visited and met Director of Sales. Special rates has been offered AED 220/240 and requested to push for all market this rates.
>
> **Arabian Journey** – Discussed with group in-charge 10-23 Nov 5 pax 2 Room + 1 extra bed offered AED 275+15 with meal charges.
>
> **Al Hadaf** – Discussed with Sales, rates given 250+15 for Oct.

Note how `AED 220/240`, `AED 275+15`, `10-23 Nov`, `5 pax`, `2 Room + 1 extra bed`
and `250+15` are preserved **exactly**, while `Disscussed → Discussed` and
`incharge → in-charge` are cleaned up. Agency names you styled yourself (e.g.
`Nugios tech`, `Nexus DMC`) are left exactly as typed.

## License

MIT
