# Content Guide — CLOUDX Proposals

This guide covers the content and tone rules for each page, with specific instructions for new vs existing clients. Read this alongside the HTML template in `assets/proposal-template.html`.

## Table of Contents

1. [General Writing Rules](#general-writing-rules)
2. [Client Type Overview](#client-type-overview)
3. [Page-by-Page Content Guide](#page-by-page)
4. [Signature Formats](#signature-formats)
5. [Standard Terms (Boilerplate)](#standard-terms)
6. [PDF Generation](#pdf-generation)

---

## General Writing Rules

- **Language**: All content in Hebrew. API names and company name "CLOUDX" in English.
- **No emojis** — anywhere. They project unprofessionalism. Use numbered blue circles (`.numbered-list`, `.del-num`) or clean styled elements instead.
- **No hour breakdown** — show total hours only, never split by category (e.g., don't list "10 שעות אפיון, 8 שעות כתיבה, 7 שעות פגישות").
- **Scope table** (if relevant) — exactly two columns. Never add a duration/time column. Column headers depend on service type (e.g., "מחלקה / יחידה" + "מוקד הפגישה" for אפיון, or "שלב" + "תיאור" for יישום).
- **Disclaimer mandatory** — every proposal must have a הבהרה (disclaimer). Content depends on the service type — it's NOT always "ייעול תהליכים קיימים". Adapt to context (e.g., for implementation: "ההצעה מתייחסת לשלב היישום בלבד"; for consulting: "ההצעה מתייחסת לייעוץ בלבד").
- **Service type flexibility** — the page structure adapts to the service: אפיון has phases A/B/C; יישום has milestones; ייעוץ might have sessions. Don't force every proposal into the same template.
- **Page overflow** — always check that content fits within A4 height (297mm). If a section runs long, split it across two `.page` divs. Better to have a page with some white space than content that gets cut off or creates a blank page.
- **Consistent logos** — cover page: large logos in white top bar. Every content page: small logos at the bottom center (24px height, 50% opacity) with a thin gray divider between them.
- **Numbers**: Use Rubik font (already set via `.num` and `font-family: 'Rubik'` classes). Format prices with commas: 7,000 not 7000.
- **Dates**: Hebrew format — "15 באפריל 2026" in body text, "אפריל 2026" on the cover badge.

---

## Client Type Overview

The **single most important input** is whether the client is new or existing. This changes:

| Aspect | Existing Client (לקוח קיים) | New Client (לקוח חדש) |
|--------|-------|------|
| **Overall tone** | Partnership — "we know you, let's move fast" | Trust-building — "here's why we're the right partner" |
| **Cover letter** | Short, references ongoing relationship | Longer, introduces CLOUDX, sells the partnership |
| **About section** | 1 short paragraph + stats + team | 1.5-2 pages: vision, services, client list, expanded team bios |
| **Background** | Straight to challenges from the meeting | Includes needs assessment framing first |
| **Scope** | Leaner (fewer hours, leverages existing knowledge) | Expanded (includes discovery, more phases) |
| **Deliverables** | Standard set (spec doc, implementation quote, summary meeting) | Expanded (adds architecture recommendation, integration mapping, gap analysis) |
| **Pricing** | Lower hours/cost (e.g., 25 hours) | Higher hours/cost (e.g., 60-70 hours) |
| **Signatures** | Simple: 4 fields per side | Expanded: 9+ fields on client side |

---

## Page-by-Page Content Guide {#page-by-page}

### Page 1: Cover (שער)

Identical structure for both client types. Fill in:
- Both logos in the white top bar
- "הצעת מחיר" as the gold title (always this text)
- Service subtitle describing what the proposal covers
- Optional second line with more detail
- Date in a badge
- "לכבוד:" + organization name + contact name and role

### Page 2: Cover Letter (מכתב מלווה)

**Signer**: The cover letter may be signed by the project lead (e.g., Roni Erez) OR by the CEO (Assaf Yishpe, אסף ישפה — מנכ"ל CLOUDX). Always use the signer specified by the user. The tone of the letter should match the signer's role — a CEO signature carries more weight for strategic/large proposals.

**Existing client tone:**
> "בהמשך לפגישה שקיימנו... ההיכרות המעמיקה מאפשרת תהליך ממוקד ויעיל"

Structure:
1. Reference the meeting (specific date)
2. Mention years of partnership and deep knowledge of their organization
3. Explain what the proposal addresses
4. Express confidence and offer availability
5. Sign-off with signer name and role

**New client tone:**
> "בהמשך לפגישת ההיכרות וההערכה... שמחים להגיש הצעה. CLOUDX הינה חברה המתמחה ב..."

Structure:
1. Reference the meeting
2. Briefly introduce CLOUDX and our expertise in information systems and technology (one paragraph — the full pitch is on page 3)
3. Show understanding of their specific situation
4. Explain what the proposal addresses
5. Express enthusiasm about the potential partnership
6. Sign-off

### Page 3: About CLOUDX + Team (אודות CLOUDX)

**IMPORTANT: CLOUDX is an information systems consulting and technology company** — not only Salesforce. The about section should describe CLOUDX as a broad technology consultancy that specializes in information systems, digital transformation, CRM platforms, and organizational technology. Salesforce is one of the platforms we work with, but not the only one.

Services to mention (adapt to context):
- ייעוץ טכנולוגי ואפיון מערכות מידע
- הטמעת מערכות CRM ומערכות ניהול
- שיפור תהליכים עסקיים ואוטומציה
- הדרכה והטמעה ארגונית
- ליווי וניהול פרויקטים טכנולוגיים
- אינטגרציות בין מערכות

**Existing client:**
- One paragraph about CLOUDX (general tech consulting — they know us already)
- 3 stat cards: years with THIS client, number of employees, number of projects
- One paragraph about the specific team working on this
- Team cards: **always based on user input** — never assume who the team is. Show 1-3 people with name, role, short bio (2-3 lines)

**New client** (may span 2 pages):
- Expanded intro paragraph: who we are, our vision, specialization in information systems and technology
- Services list (broader than just Salesforce — see list above)
- **Client list** showing breadth: nonprofits, academic institutions, tech companies
- 3 stat cards: years in business, employees, total projects completed
- Why choose us: unique selling points
- Extended team section:
  - More team members (2-4) — **based on user input**
  - Longer bios (4-5 lines each)
  - More emphasis on credentials and experience

If the about section is long enough to overflow one page, split into two `.page` divs. Put the company info on the first page and the team on the second.

### Page 4: Background & Goals (רקע ומטרות)

**Existing client:**
- Intro: "בפגישת הסקירה שנערכה ב-[DATE] עם [WHO], עלו מספר אתגרים מרכזיים:"
- Challenge bullets (from user input)
- Decision highlight-box (if applicable): what was decided
- Improvement topics as numbered list (with blue circles)
- Guiding quote in gold-box (if provided)
- Additional topics as bullet list

**New client:**
- Needs assessment intro: "מהפגישה הבנו ש..." — frames it as understanding their situation
- Assessment of existing infrastructure
- Analysis of systems they currently use
- Then: challenges, goals, etc. (similar structure but with more context)

### Page 5: Scope of Work (היקף העבודה)

**The structure of this page adapts to the service type.** Don't force every proposal into a "phases A/B/C with meetings table" template. Examples:

**For אפיון (specification) proposals:**
- Phase A: meetings with stakeholders
- Table with departments/units and meeting focus (2 columns only)
- Existing client: "ממוקד ויעיל" — leverages existing knowledge
- New client: expanded discovery (intro meetings, system mapping, infrastructure assessment)

**For יישום (implementation) proposals:**
- Milestones with deliverables per milestone
- Table: milestone name + description (2 columns)
- Timeline overview

**For ייעוץ (consulting) / תמיכה (support) proposals:**
- Session-based or retainer structure
- Scope of services included/excluded
- Escalation or priority levels if applicable

**For הדרכה (training) proposals:**
- Training modules or sessions
- Table: module name + content/audience (2 columns)
- Materials included

### Page 6: Additional Work Phases + Deliverables

Structure this page based on the service type. For אפיון proposals, this typically includes additional phases (analysis, summary meeting). For other types, adapt accordingly.

**Deliverables** — Use `.deliverable-item` cards with numbered blue circles (`.del-num`):
- Never use emojis for deliverable numbering
- Each has a title (h4) and short description (p)
- Deliverables come from user input — don't assume a fixed set

**Example deliverables for אפיון (existing client):**
1. מסמך אפיון מסכם
2. הצעת מחיר ליישום
3. פגישה מסכמת

**Example deliverables for אפיון (new client):**
1. מסמך אפיון מקיף
2. המלצה לארכיטקטורה
3. מיפוי אינטגרציות
4. ניתוח פערים מורחב
5. הצעת מחיר ליישום
6. פגישה מסכמת

### Page 7: Pricing (תמחור)

Structure is the same for both types; the NUMBERS differ:

1. Short intro line
2. Three stat cards: total hours, hourly rate (with ₪), working days
3. Big `.price-box`: label, total amount in gold, "לא כולל מע"מ"
4. `.highlight-box` with billing method (e.g., monthly invoicing based on hours worked)
5. `.gold-box` with disclaimer

Price calculation: total = hours × rate. Format with comma separator.

### Page 8: Terms + Signatures (תנאים כלליים)

**Terms** — use the standard boilerplate (included in the template). These rarely change. The terms include:
- Payment terms (15 days)
- Monthly invoicing
- Prices exclude VAT
- 30-day validity
- Independent contractor status
- Limited liability
- Confidentiality
- AI tool usage clause
- Non-solicitation (12 months)

**Signatures** — see next section.

---

## Signature Formats {#signature-formats}

### Existing Client — Simple (4 fields per side)

**Client side:**
| Field | Value |
|-------|-------|
| שם החותם ותפקידו | ________________ |
| ח.פ. | ________________ |
| חתימה | ________________ |
| תאריך | ________________ |

**CLOUDX side:**
| Field | Value |
|-------|-------|
| שם החותם ותפקידו | ________________ |
| ח.פ. | 516190498 |
| חתימה | ________________ |
| תאריך | ________________ |

### New Client — Expanded (9+ fields on client side)

**Client side:**
| Field | Value |
|-------|-------|
| שם החברה | ________________ |
| ח.פ. | ________________ |
| כתובת | ________________ |
| שם המזמין | ________________ |
| תפקיד בחברה | ________________ |
| טלפון | ________________ |
| אימייל | ________________ |
| איש קשר לחשבוניות — שם | ________________ |
| איש קשר לחשבוניות — טלפון | ________________ |
| איש קשר לחשבוניות — אימייל | ________________ |
| חותמת החברה וחתימה | ________________ |
| תאריך | ________________ |

**CLOUDX side (also expanded):**
| Field | Value |
|-------|-------|
| שם | ________________ |
| ח.פ. | 516190498 |
| חותמת | ________________ |
| חתימה | ________________ |
| תאריך | ________________ |

---

## Standard Terms (Boilerplate) {#standard-terms}

The terms list in the template is the standard CLOUDX boilerplate. Use it as-is unless the user specifically asks to modify terms. Key clauses:

1. **Payment**: Net 15 from invoice date
2. **Invoicing**: Monthly, based on hours worked
3. **VAT**: All prices exclude VAT
4. **Validity**: 30 days from submission
5. **Status**: Independent contractor, no employer-employee relationship
6. **Liability**: No liability for indirect/consequential damages
7. **Confidentiality**: Full confidentiality commitment
8. **AI Usage**: CLOUDX may use third-party AI tools while maintaining data security
9. **Non-solicitation**: 12-month mutual non-solicitation of employees

---

## PDF Generation {#pdf-generation}

Generate PDF using Chrome headless:

```bash
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless --disable-gpu --no-pdf-header-footer \
  --print-to-pdf="[OUTPUT_PATH].pdf" \
  --virtual-time-budget=5000 \
  "file://[ABSOLUTE_HTML_PATH]"
```

Key flags:
- `--no-pdf-header-footer` — removes Chrome's default URL/date header/footer
- `--virtual-time-budget=5000` — gives 5 seconds for Google Fonts (Heebo + Rubik) to load before rendering. Without this, the PDF may use fallback fonts.
- The HTML path must be an absolute `file://` URL

After generation, open the PDF for the user to review the page layout. Check that:
- No blank pages from content overflow
- Logos render correctly
- Fonts loaded properly (Hebrew text should be in Heebo, not a system fallback)
- Page breaks are clean
