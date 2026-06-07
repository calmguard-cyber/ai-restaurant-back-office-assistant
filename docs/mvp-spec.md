# MVP Specification

## Core workflow

### 1. Upload sales CSV
Input columns can be flexible, but MVP expects:

- date
- item_name
- category
- quantity
- gross_sales
- discount
- net_sales

### 2. Generate daily report
Report sections:

- 今日总销售额
- 最畅销菜品 top 5
- 低表现菜品
- 异常点：折扣过高、销量突然下降、某品类占比变化
- 明日建议：促销、备货、社媒内容

### 3. Send owner summary
Daily message format:

> 今天销售 $2,430，比昨天 +12%。Top item 是 Chicken Pad Thai。建议明天推 Mango Sticky Rice + lunch combo。库存注意 chicken / coconut milk。

### 4. Review reply generator
Input:

- rating
- review text
- tone: friendly / professional / apologetic
- language: English / Chinese / Thai / Japanese

Output:

- Short public reply
- If negative: private recovery suggestion

### 5. Menu translator
Input:

- item name
- description
- dietary info

Output:

- EN / ZH / TH / JA translations
- Short Instagram caption variant

## Success metrics for first 3 shops

- 3 shops upload at least 3 days of sales CSV
- Owner opens/reads daily summary at least 5 times in first week
- At least 1 actionable recommendation accepted per shop
- At least 1 shop willing to pay AUD 49+/month after trial
