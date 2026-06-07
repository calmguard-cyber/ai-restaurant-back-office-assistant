# Technical Plan

## Recommended stack

### Phase 1: Frontend-only MVP

Use static GitHub Pages for demo and early validation.

- HTML/CSS/JS or Vite later
- Browser CSV parsing
- Local report generation
- Copyable Telegram/WhatsApp summary
- No server required

Why: fastest to show restaurant owners and avoid backend complexity.

### Phase 2: Lightweight SaaS MVP

When a real shop wants to use it daily:

- Frontend: React + Vite
- Backend: Node/Express or serverless functions
- Database: Supabase Postgres
- Auth: email magic link or simple owner login
- File storage: Supabase Storage
- AI: OpenAI / Gemini via server-side API only
- Messaging: Telegram bot first, WhatsApp later

## Data model draft

### Restaurant

- id
- name
- cuisine_type
- timezone
- owner_contact
- preferred_language
- pos_name

### SalesUpload

- id
- restaurant_id
- uploaded_at
- source_filename
- raw_file_url
- parsed_status
- date_range

### SalesLine

- id
- upload_id
- sale_date
- item_name
- category
- quantity
- gross_sales
- discount
- net_sales

### DailyReport

- id
- restaurant_id
- report_date
- total_sales
- total_quantity
- top_items_json
- weak_items_json
- recommendations_json
- owner_summary
- created_at

### GeneratedContent

- id
- restaurant_id
- type: review_reply | menu_translation | social_caption
- input_json
- output_text
- language
- created_at

## CSV parser requirements

Must support common variations:

- item_name / item / product / menu item
- quantity / qty / units sold
- net_sales / sales / revenue / total
- gross_sales optional
- discount optional
- date optional for single-day uploads

## Report engine v1

Input: normalized sales lines.

Output:

- total sales
- total item count
- top 5 items by quantity
- top 5 items by revenue
- bottom items by quantity
- category mix
- discount warning
- simple promo idea
- stock watch list based on top items
- owner summary under 500 chars

## AI prompt modules

### Daily summary prompt

Inputs:

- restaurant profile
- top sellers
- weak sellers
- sales trend if available
- owner language

Output:

- short business summary
- 3 recommendations
- inventory watch
- tomorrow promo idea

### Review reply prompt

Inputs:

- rating
- review text
- language
- tone
- restaurant name

Output:

- public reply
- if negative, recovery note

### Menu translation prompt

Inputs:

- item name
- description
- cuisine type
- target languages

Output:

- translation
- allergy/dietary notes if available
- short marketing description

## Security / privacy basics

- Do not store card/payment data
- Do not request EFTPOS credentials
- Do not scrape POS accounts in v1
- Treat sales CSV as business confidential
- Server-side AI keys only
- Delete pilot CSVs on request

## Delivery plan

### Sprint 1

- Refactor demo into modular JS
- Add better CSV parsing
- Add column mapping UI
- Add report export/copy buttons

### Sprint 2

- Add AI API backend prototype
- Add restaurant profile form
- Add generated content history

### Sprint 3

- Add Telegram bot delivery
- Add scheduled daily report
- Run with first pilot shop
