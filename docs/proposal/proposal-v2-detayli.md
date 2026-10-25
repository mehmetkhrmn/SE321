# SE 321 Software Specification and Design: Project Proposal (Revised, v2)

> Revised after instructor feedback on v1. Student IDs and e-mail addresses are omitted here because this repository is public; they stay in the submitted document.
> **Not:** Bu taslak, grubun "KerzzPOS'un yerine yeni POS" kararından **önce** yazıldı; burada KerzzPOS yerinde kalıyor. Güncel kapsam için [kısa versiyona](proposal-v2.md) bakın.
> **[TBD]** marks items that must be confirmed with the client or decided by the group before submission.

| | |
|---|---|
| **Project Name** | [TBD: choose one of the short names in the [feedback notes](feedback-yanitlari.md#10-proje-adı)] |
| **Subtitle** | Stock, Invoice and Current-Account Management for Multi-Branch Restaurants and Bars |
| **Section / Group No.** | Section 2 - Group 2 |
| **Proposal Date** | 18/10/2026 (revised: [TBD]) |
| **Group Members** | Mehmet Kahraman, İsmail Yiğit Şendur, Hakkı Can Duran, Hüseyin Esen, Batuhan Deliaslan, Umutcan Yavuz, Erden Can Aktan |
| **Client** | Mustafa Ulukaya, Financial Director, Rise Group |
| **First Meeting Date** | 15/10/2026 |

---

## 1. Business Context

Rise Group operates restaurant and bar venues: 4-5 branches in the summer season and 3 in winter, with about 250 staff over the year. Each branch has a kitchen and a bar and receives goods from many suppliers, typically twice a week, with the heaviest trade at weekends.

Today the stock and purchasing workflow runs like this:

1. **Request.** The bartender (alcohol, soft drinks) and the chef post what they need in a WhatsApp group. Planning is weekly.
2. **Approval and order.** The purchasing manager approves the requests and orders from suppliers.
3. **Receiving.** The warehouse staff member receives the goods at the door. Both the supplier and the business stamp and sign the delivery note. Goods go to the bar or the basement storeroom. A photo of the delivery note is shared on WhatsApp. Damaged goods are returned.
4. **Recording.** The purchasing manager enters purchase invoices into KerzzPOS. Sales are exported from KerzzPOS to Excel. None of this reaches Netsis automatically.

Two systems are in use today:

- **KerzzPOS**: sales, orders and payments at the point of sale.
- **Netsis**: accounting. According to the client, Netsis itself is **not** the main problem.

The day-to-day work between these two systems is where the problems are.

| Role | What they do today (stock / finance) |
|---|---|
| Financial Director | Follows cash, credit-card totals, supplier balances and branch results; final decision maker |
| Purchasing Manager | Approves stock requests, orders from suppliers, **enters invoice and stock data**, reports to finance |
| Warehouse Staff | Receives deliveries and stores them; does **not** enter data today |
| Chef | Requests kitchen ingredients |
| Bartender | Requests bar stock (alcohol, soft drinks) |
| Waiters, commis, bar-backs | Work with KerzzPOS only; not users of the new system |
| Branch Manager / Accountant [TBD] | Not mentioned in the meeting; to be confirmed |

## 2. Problem Identified with the Client

- **No data flow between KerzzPOS and Netsis.** Sales and purchase data are re-typed by hand, so the same information is entered more than once and errors creep in.
- **Manual invoice and delivery-note handling.** The client called this "our biggest problem". In peak season 70-80 supplier invoices arrive per week (76 in the week of the meeting). Discounts differ from invoice to invoice. Each invoice is checked and entered by hand.
- **Inaccurate stock.** KerzzPOS deducts stock as sales are keyed in, but the client says its stock is "not 100% accurate". Waste and expiry are checked by hand. A monthly count takes 1-2 people 4-5 hours. The client would like to count **weekly**.
- **No low-stock alerts.** Nothing warns the team when, for example, soft drinks fall below 50 units. Requests go through a WhatsApp group.
- **Weak current-account and cash visibility.** Supplier balances, payments due and daily cash/credit-card totals are not available in one place.
- **No combined branch view.** Stock levels and inter-branch transfers across 3-5 seasonal branches cannot be seen together.
- **Security concerns.** The client considers the current POS's security weak.

The client named the main priorities as: **(1) current-account / cash management, (2) invoice / delivery-note processes, (3) stock.**

## 3. Proposed Software Solution

A central web application that sits **between KerzzPOS and Netsis** and covers the three priority areas. It does **not** replace either system.

### 3.1 System boundary

| | In scope (our system) | Stays in existing system | Out of scope |
|---|---|---|---|
| Sales at the counter / table | Read daily sales from KerzzPOS to deduct stock and show sales totals | **KerzzPOS** | New POS, table or order management |
| Official accounting | Prepare approved invoices and current-account movements for transfer to Netsis | **Netsis** (general ledger, tax, official books) | Replacing Netsis |
| Invoices / delivery notes | Capture, AI-assisted extraction, **human verification**, matching | | Issuing e-invoices to customers |
| Current accounts / cash | Supplier current accounts, payments, cash and card daily summary, expenses | | Payroll, banking integration |
| Stock | Items, goods receipt, consumption, waste, counts, transfers, alerts | | Recipe costing, demand forecasting (later) |

How data moves between KerzzPOS, Netsis and our system (API, file export/import, or manual upload) is **[TBD: ask the client / check what KerzzPOS and Netsis can export]**. The design will keep this behind a separate integration component so the core does not depend on it.

### 3.2 Core modules (by client priority)

**M1. Current-Account and Cash Management.** "Accounting management" in this project means **pre-accounting** only:

- supplier current accounts: invoices (debit), payments (credit), running balance;
- payment tracking: due dates, paid / partly paid / overdue status, upcoming-payments list;
- expense records (non-stock expenses such as utilities, repairs) by branch and category;
- daily cash and credit-card summary per branch, using sales totals from KerzzPOS;
- financial reports: supplier balances, payments due, expenses by category, daily/weekly sales vs. purchases per branch.

General ledger, tax declarations, payroll and official financial statements are **not** included. They stay in Netsis / with the accountant.

**M2. Invoice and Delivery-Note Processing.**

- Purchasing personnel upload a supplier invoice or delivery note (PDF, e-invoice file, or a photo of a paper document).
- The system extracts the data (see Section 4), and a user **verifies and corrects** it before anything is saved.
- A delivery note is matched to its invoice. Quantity or price differences are flagged.
- An approved invoice updates the supplier's current account (M1). An approved delivery note updates stock (M3).

**M3. Stock Management.**

- Item cards with units and unit conversions (e.g. 1 case = 24 bottles), separately for kitchen and bar stock.
- Goods receipt from approved delivery notes.
- Stock deduction from KerzzPOS sales [TBD: needs a product-to-ingredient mapping; first version may deduct only items sold as-is, e.g. drinks].
- Waste / spoilage records.
- Stock counts with a count sheet, showing the difference against the system quantity.
- Inter-branch transfers [TBD: the recording is unclear on whether transfers happen today].
- Critical-level alerts per item and branch (e.g. soft drinks below 50 units), and a suggested weekly order list.
- *Should:* stock requests from the chef and bartender, approved by the purchasing manager (replaces the WhatsApp group).

## 4. AI-Assisted Invoice / PDF Processing

| Question | Decision |
|---|---|
| **Document types** | (1) Supplier e-invoice / e-archive invoice (PDF, or UBL-TR XML when available); (2) delivery notes (e-delivery note PDF, or photo/scan of a paper note). Expense receipts: *Could*, later. |
| **Extracted fields** | Header: supplier name, tax number, document number, document date, due date (invoice). Lines: product description, quantity, unit, unit price, discount, VAT rate, line total. Totals: subtotal, total discount, VAT, grand total. |
| **Method** | If the e-invoice XML is available, it is read directly (no AI needed, exact data). Otherwise the PDF or photo is processed by an AI/OCR extraction service. |
| **Product matching** | Supplier product names are mapped to our stock items. A confirmed mapping is remembered for that supplier and suggested automatically next time. |
| **Uncertain or wrong results** | Every field gets a confidence value. Low-confidence fields, unmapped products and failed checks are **highlighted**. Automatic checks: line totals add up to the document total; VAT is computed correctly; supplier and document number are not a duplicate; delivery-note quantities match the invoice. |
| **Human verification (mandatory)** | Every extracted document goes to a **"Pending verification"** state. A purchasing user sees the original document next to the extracted data, corrects it, and approves it. **Only approved documents change stock or current-account records.** If extraction fails, the user enters the data manually on the same screen. |
| **Traceability** | The original file, the extracted values, the user's corrections, and who approved it and when are all stored (see audit log, Section 5). |

## 5. Non-Functional Requirements (measurable)

Numbers are first proposals and will be confirmed with the client in the requirements stage.

**Security**

| ID | Requirement |
|---|---|
| SEC-1 Authentication | Every user has a personal account (no shared accounts). Passwords are at least 10 characters and stored hashed (bcrypt or Argon2). An account is locked for 15 minutes after 5 failed logins. Sessions time out after 30 minutes of inactivity. |
| SEC-2 Role-based access | Roles: Financial Director, Branch Manager, Purchasing, Kitchen, Bar, Accountant (read-only), Administrator. Each screen and action is allowed per role. A user only sees their assigned branches unless their role covers all branches. |
| SEC-3 Financial data | Purchase prices, supplier balances and financial reports are visible only to Financial Director, Purchasing and Accountant roles. Kitchen and Bar roles see quantities only. All traffic uses HTTPS (TLS 1.2 or higher). |
| SEC-4 Audit log | Every create, update, delete and approval on invoices, payments, stock movements and counts is logged with user, time, old value and new value. Users cannot edit or delete log entries. Logs are kept for at least 2 years [TBD]. |
| SEC-5 Backup and recovery | Automatic database backup every day, kept for 30 days, stored off the main server. Data loss in a failure is at most 24 hours (RPO). The system can be restored within 4 hours (RTO). A restore is tested at least once per season. |

**Timeliness (instead of "real-time")**

| ID | Requirement |
|---|---|
| TIM-1 | A stock movement or payment recorded **in our system** appears in stock levels, balances and dashboards within **5 seconds**. |
| TIM-2 | Sales from KerzzPOS are reflected in stock and sales totals within **[TBD: 15 minutes if an API/automatic export exists; otherwise after the end-of-day import]**. Each dashboard shows the time of the last KerzzPOS update. |
| TIM-3 | A critical-stock alert is shown within 1 minute of the stock falling below its critical level. |

**Usability and performance**

| ID | Requirement |
|---|---|
| USE-1 | Works in a current browser on PC, tablet and phone. Dashboards and stock entry are usable on a phone screen. |
| USE-2 | A goods receipt from an already-extracted delivery note can be verified and approved in under 2 minutes for a 10-line document. |
| USE-3 | A full count per branch takes **under 1.5 hours** (today 4-5 hours) using a count list on a tablet/phone, so that weekly counts become practical. |
| USE-4 | Staff used to the current workflow can use the core screens after at most 1 day of training. The client expects a 15-day to 1-month adaptation period. |
| PERF-1 | Normal screens load in under 2 seconds for up to 20 concurrent users across all branches. |

## 6. Expected Outcomes / Success Criteria

- No re-typing of purchase invoices: each invoice is entered once (verified extraction) and prepared for Netsis.
- Count time reduced from 4-5 hours to under 1.5 hours per branch, so counts can move from monthly to weekly.
- Supplier balances, payments due and daily cash/card totals for all branches on one screen.
- Fewer stock-outs of critical items (e.g. soft drinks) during service [TBD: baseline from client].

## 7. Meeting Photo with the Client

[Keep the photo from v1.]
