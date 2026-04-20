---
name: cloudx-proposal
description: "Generate professional CLOUDX price proposals (הצעות מחיר) as polished HTML documents ready for PDF export. Use this skill whenever the user wants to create a proposal, quote, הצעת מחיר, price estimate, or client-facing pricing document for CLOUDX. Also triggers when the user mentions preparing a quote for a client meeting, building a proposal document, creating a pricing document, or generating an offer for consulting services — even if they don't use the word 'proposal' explicitly. Covers both new and existing clients with distinct tones and structures."
---

# CLOUDX Proposal Generator — הצעת מחיר

Generate professional, print-ready HTML proposals for CLOUDX clients. CLOUDX is an information systems consulting and technology company (not limited to Salesforce) — proposals may cover CRM implementation, system specification, process optimization, integration, training, ongoing support, or any consulting engagement.

Each proposal is a Hebrew RTL document (typically 8 pages) with consistent CLOUDX branding, ready for PDF conversion via Chrome headless. The design and CSS are defined in `assets/proposal-template.html` — always read it before generating.

The proposal has a distinctive visual identity: blue gradient cover, gold accents, data cards, numbered-circle lists (never emojis), and a clean professional layout.

## Required Inputs

Before generating, gather ALL of these from the user. If the conversation already contains some (e.g., from a meeting summary or brief), extract them and confirm with the user. Ask about anything missing — don't guess.

| # | Input | Example | Required | Notes |
|---|-------|---------|----------|-------|
| 1 | שם הלקוח | עולים ביחד | Yes | |
| 2 | איש קשר + תפקיד | וינו — מנכ"ל | Yes | |
| 3 | לקוח חדש/קיים + שנות ליווי | קיים, 7 שנים | Yes | Changes tone, structure, signatures |
| 4 | תאריך פגישה | 15.04.2026 | Yes | |
| 5 | סוג השירות ותיאורו | אפיון CRM / יישום / ייעוץ / הדרכה / תמיכה | Yes | **Not limited to אפיון — adapt structure to service type** |
| 6 | אתגרים / רקע | רשימת נקודות | Yes | |
| 7 | נושאים / יעדים לטיפול | רשימה | Yes | |
| 8 | נושאים נוספים שזוהו | רשימת נקודות | If applicable | |
| 9 | שלבי עבודה / היקף | תיאור חופשי + טבלה אם רלוונטי | Yes | Adapt to service type — not always "phases A/B/C" |
| 10 | תוצרים | כותרת + תיאור × N | Yes | |
| 11 | שעות + תעריף | 25 × 280 | Yes | Show total only — never break down by category |
| 12 | ימי עבודה | 2 | If applicable | Not always relevant |
| 13 | דיסקליימר / הבהרות | טקסט חופשי | Yes | Adapt to context — not always "ייעול תהליכים קיימים" |
| 14 | **חותם/ת המכתב** | רוני ארז / אסף ישפה — מנכ"ל | **Yes — always ask** | May be project lead OR CEO (Assaf Yishpe) |
| 15 | **צוות מוביל** (name, role, bio) | 1-3 אנשים | **Yes — always ask** | Team changes per project — never assume |
| 16 | נתיב לוגו לקוח | path/to/logo.png | Yes | **If not provided, ask the user to point you to the file** |
| 17 | נתיב לוגו CLOUDX | path/to/cloudx-logo.png | Yes | **If not provided, ask the user for the path** |
| 18 | מטרה מנחה / ציטוט | ... | If applicable | |
| 19 | נתוני "אודות" | שנות ניסיון, עובדים, פרויקטים | Yes | |

## Workflow

### Step 1: Gather Inputs

Ask the user for all required inputs. Three questions are CRITICAL and must always be asked explicitly:

1. **לקוח חדש או קיים?** — changes tone, about length, and signature format
2. **מי חותם/ת את המכתב המלווה?** — could be the project lead (e.g., Roni Erez) OR the CEO (Assaf Yishpe, מנכ"ל CLOUDX). Never assume.
3. **מי הצוות המוביל?** — team changes per project. Always ask for names, roles, and short bios. Never reuse team from a previous proposal without confirming.

**Logos**: If the user doesn't provide logo paths, ask them to point you to the logo files. Don't generate without logos — they appear on every page.

**Service type**: The proposal structure adapts to the service type. An "אפיון" (specification) proposal has phases A/B/C with meetings tables. An "יישום" (implementation) proposal has milestones and deliverable sprints. A "ייעוץ" (consulting) proposal might be structured differently. Adapt the page structure to fit the actual service — don't force every proposal into the אפיון template.

If the user provides a meeting summary or brief, extract inputs and present them back for confirmation before generating.

### Step 2: Read Template + Content Guide

Read these two files:
1. `assets/proposal-template.html` — the complete CSS and HTML structure. The CSS must be copied VERBATIM into the generated document. This ensures visual consistency.
2. `references/content-guide.md` — page-by-page content instructions, tone guidelines, and the full new-vs-existing client differences.

### Step 3: Generate the HTML Document

Create a complete, self-contained HTML file following these rules:

**Structure:**
- Each page is a `<div class="page ...">` with `page-break-after: always` (except last)
- Cover page uses class `page cover`
- Content pages use class `page content-page` and include: `.side-bar`, `.page-logos` footer
- Verify no page overflows — content should fit within 297mm height. If a section runs long, split across two pages

**Content generation per client type:**
- **Existing client**: Partnership tone, concise about section, direct to challenges, leaner scope, simple 4-field signatures
- **New client**: Trust-building tone, expanded about (up to 2 pages), needs assessment before challenges, expanded scope, 9+ field signatures

**Design rules (non-negotiable):**
- NO emojis anywhere — use numbered blue circles (`.numbered-list`, `.del-num`) or clean styled elements
- NO hour breakdown by category — show total hours only
- Meeting/scope table: TWO columns only (no duration column) — if table is relevant to the service type
- Disclaimer/הבהרה is mandatory — content depends on service type (not always "ייעול תהליכים קיימים")
- All text in Hebrew, company name "CLOUDX" in English
- `dir="rtl"` on `<html>` element
- Border-right (not border-left) for highlight/gold boxes
- Padding-right for lists

### Step 4: Save the HTML File

Write the file to the user's specified path. Default naming:
```
הצעת_מחיר_[CLIENT_NAME]_[SHORT_DESCRIPTION].html
```
Replace spaces with underscores in the filename.

### Step 5: Generate PDF (if requested)

```bash
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless --disable-gpu --no-pdf-header-footer \
  --print-to-pdf="OUTPUT_PATH.pdf" \
  --virtual-time-budget=5000 \
  "file://ABSOLUTE_HTML_PATH"
```

The `--virtual-time-budget=5000` ensures Google Fonts (Heebo + Rubik) load before rendering. The `--no-pdf-header-footer` removes Chrome's default header/footer text.

After PDF generation, open it for the user to review.

## Quick Reference — CSS Component Classes

These classes are defined in the template CSS. Use them for consistent styling:

| Component | Class(es) | Usage |
|-----------|-----------|-------|
| Blue info box | `.highlight-box` | Decisions, key information |
| Gold quote box | `.gold-box` | Guiding quotes, mottos, disclaimers |
| Numbered list | `.numbered-list` | Improvement topics, ordered items |
| Data card row | `.price-detail-card` inside flex container | Statistics (hours, rate, years) |
| Meeting table | `.meeting-table` | Department meeting schedule |
| Price box | `.price-box` with `.price-label`, `.price-amount`, `.price-note` | Total price display |
| Deliverable card | `.deliverable-item` with `.del-num` | Numbered deliverables |
| Team card | `.team-card` with `.avatar` | Team member profiles |
| Signature grid | `.sig-grid` > `.sig-box` | Signature blocks |
| Section title | `.section-title` | Main headings (28px, blue, underline) |
| Section subtitle | `.section-subtitle` | Sub-headings (20px, blue) |
| Terms list | `.terms` | Small gray legal text |

## File References

| File | When to Read | What It Contains |
|------|-------------|-----------------|
| `assets/proposal-template.html` | **Always** — before generating any proposal | Complete CSS + HTML page structure with component examples |
| `references/content-guide.md` | **Always** — before generating content | Page-by-page content instructions, tone rules, new/existing client differences, signature formats |
