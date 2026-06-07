# Product Development Plan

## Product thesis

Restaurant owners do not want to replace their POS. They want a simple assistant that reads the data they already have and tells them what to do tomorrow.

**Positioning:** POS-adjacent AI back-office assistant for small restaurants.

**Do not build first:** full POS, EFTPOS/PCEFTPOS, accounting, payroll, complex inventory procurement.

## First sellable promise

> Send me your POS CSV once a day. I will send you a short business summary with top sellers, weak items, promo ideas, review replies, and menu/social content.

## Target first customers

1. Sydney Asian restaurants
2. Thai / Viet / Japanese restaurants
3. Cafes with simple menus
4. Small food businesses that already use POS but do not analyse data

## MVP product shape

### User flow

1. Owner uploads POS CSV / Excel
2. System parses sales rows
3. System generates daily report
4. Owner receives short Telegram / WhatsApp style summary
5. Owner can generate:
   - Google review replies
   - Menu translations
   - Instagram/TikTok captions
   - Promo suggestions

### First version: concierge + lightweight app

- Static/public demo for sales conversations
- Local CSV analysis in browser for demo
- Next: simple backend with upload + report generation
- Manual onboarding for first 3 shops

## Milestones

### Milestone 0 — Demo credibility, done/in progress

- [x] Public GitHub Pages demo
- [x] CSV report demo
- [x] Review reply generator
- [x] Menu translation + caption generator
- [x] English version

### Milestone 1 — Real MVP app

Goal: one restaurant can upload a CSV and receive a usable daily report.

Build:

- CSV upload UI
- Flexible column mapping
- Sales analytics engine
- Daily report template
- Export/copy Telegram summary
- Save report history in browser or lightweight backend

Definition of done:

- Works with at least 3 sample POS CSV formats
- Report takes less than 30 seconds to generate
- Owner can copy/send summary without editing much

### Milestone 2 — AI layer

Goal: reports and replies feel like a real assistant, not a spreadsheet.

Build:

- AI-generated business summary
- Promo ideas based on top sellers / weak sellers
- Review reply generator with tone controls
- Menu translation with cuisine-aware wording
- Social caption generator

Definition of done:

- 10 real reviews generate acceptable replies
- 20 menu items translate cleanly enough for public use
- Daily report includes 3 actionable suggestions

### Milestone 3 — Owner delivery

Goal: owner receives daily summary without opening a dashboard.

Build:

- Telegram bot delivery first
- WhatsApp later if needed
- Scheduled daily summary
- Manual CSV upload link
- Optional email fallback

Definition of done:

- One shop receives daily summary for 7 consecutive days
- Owner replies at least twice with useful feedback

### Milestone 4 — Paid pilot

Goal: validate payment.

Build:

- Simple landing page with pricing
- Stripe/payment link or invoice flow
- Onboarding checklist
- Testimonial capture

Definition of done:

- 3 free pilots completed
- 1 paid pilot at AUD 49+/month or setup fee

## Pricing test

Start with simple packages:

### Starter
AUD 49/month

- Daily CSV report
- Review reply generator
- Menu/social content tools

### Owner Plus
AUD 99/month

- Everything in Starter
- Weekly trend report
- Promo ideas
- Menu translation support

### Setup
AUD 300–800 one-time

- POS CSV mapping
- Report setup
- Telegram/WhatsApp delivery setup

## Product principles

- CSV first, integrations later
- Daily summary first, dashboard second
- Human-friendly language over analytics jargon
- Multilingual by default: English, Chinese, Thai, Japanese
- No POS replacement messaging
- Small shop owner time is the main pain point

## Next build order

1. Convert static demo into small web app structure
2. Add robust CSV parser and column mapping
3. Add report generator module
4. Add sample data sets for different restaurant types
5. Add mock Telegram summary export
6. Add backend only when needed for saving/uploading/AI calls
