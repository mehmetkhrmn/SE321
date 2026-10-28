# Requirements Specification (v3)

**Project:** [PROJECT NAME]: Restaurant POS with Stock, Invoice and Current-Account Tracking
**Group:** Section 2 - Group 2
**Client:** Mustafa Ulukaya, Financial Director, Rise Group
**Sources:** Meeting 1 = first client meeting, 15/10/2026 (audio recording, ~25:38). Times are approximate positions in the recording.
**Previous drafts:** [v1](gereksinimler-ilk-gorusme.md), [v2](gereksinimler-ilk-gorusme-v2.md) (Turkish, with full transcript quotes for every item).

---

## 1. Project / Problem Summary

Rise Group runs restaurant and bar venues with 4-5 branches in summer and 3 in winter. Today it uses two systems that do not exchange data: KerzzPOS for sales and payments, and Netsis for accounting. Netsis works well; the problems come from KerzzPOS and from the missing link between the two. Sales and purchase data are moved by hand through Excel and entered more than once. Stock figures in KerzzPOS are not accurate, there are no low-stock alerts, and a monthly count takes 4-5 hours. In peak season 70-80 supplier invoices arrive every week and are typed in by hand, which the client calls the biggest problem.

The proposed system replaces KerzzPOS and works with Netsis, which remains the official accounting system. It covers the client's three priorities: (1) current-account and cash records, (2) invoice and delivery-note processing, (3) stock. A POS with core functions only is the place where sales data starts.

## 2. Actors / Stakeholders

| Actor / Stakeholder | Role | Interacts with the system? | Source |
|---|---|---|---|
| Financial Director (client) | Responsible for accounting and finance; receives reports; final decision maker | Yes: reports, current accounts, cash | Meeting 1, ~00:12, ~22:10 |
| Purchasing Manager | Approves material requests, orders from suppliers, enters invoice and stock data, reports to finance | Yes: main data-entry user | Meeting 1, ~00:47, ~03:04, ~22:02–22:08 |
| Warehouse Staff | Receives goods from suppliers at the door and stores them; does not enter data today | Yes: goods receipt (to be confirmed) | Meeting 1, ~04:11–04:59, ~22:18–22:21 |
| Chef | Requests kitchen materials | Yes: material requests | Meeting 1, ~00:47, ~02:56 |
| Bartender | Requests bar stock (alcohol, soft drinks) | Yes: material requests | Meeting 1, ~02:56–02:59 |
| Waiter / Commis / Bar-back | Front-of-house staff | Yes: POS orders (waiters) | Meeting 1, ~00:57 |
| Suppliers | Deliver goods, stamp and sign delivery notes, send invoices; receive orders | Indirectly: receive order messages | Meeting 1, ~04:40–04:47, ~12:13 |
| Netsis (external system) | Official accounting system; stays in use | Yes: receives exported data | Meeting 1, ~03:45, ~08:24–08:30 |
| Ministry of Agriculture and Forestry inspectors | Carry out food-safety inspections | No (affected stakeholder) | Meeting 1, ~19:58–20:09 |

## 3. Functional Requirements

Priority: **H** = part of the client's top three (current account/cash, invoice/delivery note, stock) or called the biggest problem; **M** = asked for or described as a problem, but not in the top three; **L** = client said "would be nice" or mentioned it in passing.

### 3.1 Current Account and Cash

| ID | Requirement | Source / Evidence | Priority | Status |
|---|---|---|---|---|
| FR-01 | The system shall record current-account transactions. | Meeting 1, ~24:39, ~25:01 | H | Stated |
| FR-02 | The system shall produce a current-account statement listing all transactions and the balance of an account. | Team analysis, based on Meeting 1, ~03:45 (statements are taken from Netsis today) | M | Assumed |
| FR-03 | The system shall record cash-register entries (money in) and exits (money out). | Meeting 1, ~14:30, ~25:01 | H | Stated |
| FR-04 | The system shall record the payment type of each payment as cash or credit card. | Meeting 1, ~14:30 | H | Stated |
| FR-05 | The system shall produce an end-of-day cash report showing cash total, credit-card total, entries and exits. | Meeting 1, ~14:17–14:36 | H | Stated |
| FR-06 | The system shall produce revenue reports for a selected period. | Meeting 1, ~09:20–09:38 (named as a feature to keep) | H | Stated |
| FR-07 | The system shall provide the KerzzPOS reports that the client uses today. | Meeting 1, ~07:36–07:43 (client values KerzzPOS's detailed reports), ~13:09 | M | Assumed |
| FR-08 | The system shall produce a monthly financial report that includes profitability. | Meeting 1, ~16:01 | M | Stated |
| FR-09 | The system shall make purchase data entered by the purchasing manager available to the finance role as a report. | Team analysis, based on Meeting 1, ~22:02–22:10 | M | Assumed |

### 3.2 Supplier Invoices

| ID | Requirement | Source / Evidence | Priority | Status |
|---|---|---|---|---|
| FR-10 | The system shall allow a user to upload a supplier invoice as a PDF file. | Meeting 1, ~01:13–01:29 | H | Stated |
| FR-11 | The system shall automatically extract the supplier, line items, quantities, unit prices and discounts from an uploaded PDF invoice. | Meeting 1, ~01:25–01:32, ~18:38, ~19:22–19:32 | H | Stated |
| FR-12 | The system shall record a unit price for each invoice line. | Meeting 1, ~19:22 | H | Stated |
| FR-13 | The system shall record a discount for each invoice, where the discount can differ from one invoice to another. | Meeting 1, ~19:24–19:32 | H | Stated |
| FR-14 | The system shall export processed invoice data to Netsis. | Meeting 1, ~01:32, ~02:25 | H | Stated |
| FR-15 | The system shall require a user to review and approve extracted invoice data before it changes stock or current-account records. | Team proposal: extracted data changes financial and stock records, and extraction can be wrong (instructor feedback on the proposal also recommended a human verification step) | H | Proposed |
| FR-16 | The system shall mark extracted invoice values that are uncertain or whose line totals do not match the invoice total. | Team proposal: the reviewer needs to see which values to check before approving (see FR-15) | M | Proposed |
| FR-17 | The system shall add the items of an approved purchase invoice to stock. | Team analysis, based on Meeting 1, ~02:22, ~06:19–06:37 (stock is fed by purchase invoices in KerzzPOS today) | H | Assumed |
| FR-18 | The system shall link every invoice and delivery to a supplier. | Team analysis, based on Meeting 1, ~04:40, ~18:38 | M | Assumed |

### 3.3 Delivery Notes and Goods Receipt

| ID | Requirement | Source / Evidence | Priority | Status |
|---|---|---|---|---|
| FR-19 | The system shall record delivery notes received from suppliers. | Meeting 1, ~25:06 | H | Stated |
| FR-20 | The system shall record each receipt of goods with its supplier, date, items and quantities. | Team analysis, based on Meeting 1, ~04:11–04:47 (goods are received at the door and the delivery note is stamped and signed by both sides) | H | Assumed |
| FR-21 | The system shall allow a photo of the delivery note to be attached to a goods receipt so that purchasing and finance can confirm it. | Team analysis, based on Meeting 1, ~05:01–05:08 (done through WhatsApp today) | M | Assumed |
| FR-22 | The system shall record the return of damaged goods to the supplier. | Team analysis, based on Meeting 1, ~05:32–05:41 | M | Assumed |
| FR-23 | The system shall record where received goods are stored (bar or storeroom). | Team analysis, based on Meeting 1, ~04:51–04:59 | L | Assumed |

### 3.4 Material Requests and Ordering

| ID | Requirement | Source / Evidence | Priority | Status |
|---|---|---|---|---|
| FR-24 | The system shall allow bartenders and chefs to submit material requests. | Team analysis, based on Meeting 1, ~02:50–02:59 (done through a WhatsApp group today) | M | Assumed |
| FR-25 | The system shall allow the purchasing manager to approve material requests. | Team analysis, based on Meeting 1, ~03:04 | M | Assumed |
| FR-26 | The system shall produce a weekly order list from the approved requests. | Team analysis, based on Meeting 1, ~02:46, ~03:07 (purchasing is planned weekly) | L | Assumed |
| FR-27 | The system shall send an order message to the supplier electronically when an item falls below its critical stock level. | Meeting 1, ~12:09–12:26 | M | Stated |

### 3.5 Stock

| ID | Requirement | Source / Evidence | Priority | Status |
|---|---|---|---|---|
| FR-28 | The system shall keep the stock quantity of each item for each branch. | Meeting 1, ~25:06, ~00:26 | H | Stated |
| FR-29 | The system shall reduce stock by the items of an order when its payment is completed. | Meeting 1, ~14:39–14:55 | H | Stated |
| FR-30 | The system shall convert a purchase unit into stock units using a defined quantity per unit (e.g. 1 case = 12 bottles). | Team analysis, based on Meeting 1, ~07:44–07:58 (staff multiply cases into bottles by hand today) | M | Assumed |
| FR-31 | The system shall group items into categories (alcohol, soft drinks, snacks, food). | Team analysis, based on Meeting 1, ~18:38 | L | Assumed |
| FR-32 | The system shall allow a critical stock level to be set for each item. | Meeting 1, ~03:12–03:14 (example: soft drinks below 50) | M | Stated |
| FR-33 | The system shall alert users when the stock of an item falls below its critical level. | Meeting 1, ~03:09–03:18 | M | Stated |
| FR-34 | The system shall support a stock count for a branch and record the difference between counted and recorded quantities. | Meeting 1, ~08:51, ~17:31–17:39 | M | Stated |
| FR-35 | The system shall record transfers of items between branches. | Meeting 1, ~24:12–24:29; conflicting answer at ~11:05–11:14 | M | Assumed |
| FR-36 | The system shall record cost data for items. | Meeting 1, ~15:06–15:14 (client: "would be good"); meaning of "cost integration" unclear | L | Assumed |

### 3.6 Point of Sale

| ID | Requirement | Source / Evidence | Priority | Status |
|---|---|---|---|---|
| FR-37 | The system shall keep a separate order (adisyon) for each table, listing the ordered items. | Team analysis, based on Meeting 1, ~14:48–14:53 and the team decision to replace KerzzPOS | H | Assumed |
| FR-38 | The system shall keep a list of menu items with their sale prices. | Team analysis, based on Meeting 1, ~14:52, ~19:19 | H | Assumed |
| FR-39 | The system shall allow payment of a table's order by cash or credit card. | Team analysis, based on Meeting 1, ~14:30, ~14:55 | H | Assumed |
| FR-40 | The system shall send each completed sale to a certified fiscal cash-register device so that a fiscal receipt is issued. | Team proposal: in Turkey sales receipts must be issued through a certified cash-register device (ÖKC); the prototype will simulate the device | M | Proposed |

### 3.7 Data Flow and Users

| ID | Requirement | Source / Evidence | Priority | Status |
|---|---|---|---|---|
| FR-41 | The system shall make sales data available to stock and reporting without manual export to Excel. | Meeting 1, ~02:15–02:28, ~08:51 | H | Stated |
| FR-42 | The system shall not require the same sales or purchase data to be entered more than once. | Meeting 1, ~01:45–02:03, ~08:39–09:06, ~15:54–16:07 | H | Stated |
| FR-43 | The system shall support these user roles: financial director, purchasing manager, warehouse staff, chef, bartender and waiter. | Team analysis, based on Meeting 1, ~00:47–00:57, ~22:02–22:21 | H | Assumed |

## 4. Non-Functional Requirements

| ID | Requirement | Source / Evidence | Priority | Status |
|---|---|---|---|---|
| NFR-01 | The system shall have no high- or critical-severity findings in a vulnerability scan before it is put into use. | Team analysis, based on Meeting 1, ~09:42–10:20 (client considers the current POS's security weak); threshold set by the team | H | Assumed |
| NFR-02 | The system shall show purchase prices, supplier agreements and profit margins only to the roles the client authorises. | Meeting 1, ~19:01–19:19 (team asked; client did not clearly confirm) | H | Assumed |
| NFR-03 | The system shall require each user to log in with a personal account before any function is available. | Team proposal: the system holds financial data and is used by many staff roles | H | Proposed |
| NFR-04 | The system shall log every change to invoices, cash, current-account and stock records with the user, time, old value and new value. | Team proposal: financial and stock records must be traceable, and it supports NFR-06 and NFR-07 | H | Proposed |
| NFR-05 | The system shall back up its data at least once a day, so that no more than 24 hours of data can be lost. | Meeting 1, ~09:48–09:57 (backup came up as an example; client's answer unclear); numbers set by the team | M | Assumed |
| NFR-06 | The system's cash and current-account balances shall equal the sum of their recorded transactions, with zero difference. | Meeting 1, ~24:39–24:42 (client: must run "very accurately"); measure set by the team | H | Assumed |
| NFR-07 | After a stock count, the difference between counted and recorded stock shall be no more than 2% per item. | Meeting 1, ~03:35–03:41, ~06:15 (KerzzPOS stock is "not 100% accurate"); 2% set by the team | H | Assumed |
| NFR-08 | The system shall handle at least 80 supplier invoices per week. | Meeting 1, ~18:33–18:56 (70-80 per week in peak season) | H | Stated |
| NFR-09 | A user shall be able to review and approve one extracted invoice within 2 minutes. | Team analysis, based on Meeting 1, ~01:13 (manual invoice entry is the biggest problem); 2 minutes set by the team | M | Assumed |
| NFR-10 | A full stock count of one branch shall take no more than 2 hours (today 4-5 hours), so that it can be done weekly. | Meeting 1, ~17:09–17:44; 2 hours set by the team | M | Assumed |
| NFR-11 | The system shall support at least 5 branches operating at the same time. | Meeting 1, ~00:26 | H | Stated |
| NFR-12 | The system shall allow a branch to be deactivated for the winter and reactivated later without losing its data. | Team analysis, based on Meeting 1, ~00:26, ~01:19 | M | Assumed |
| NFR-13 | The system shall support at least 250 user accounts. | Team analysis, based on Meeting 1, ~00:36 (about 250 staff per year; how many will be users is unknown) | L | Assumed |
| NFR-14 | The system shall be usable from a mobile phone and from an office computer. | Meeting 1, ~16:59–17:05 | M | Stated |
| NFR-15 | Staff shall be able to carry out their core tasks in the system without help within 30 days of training. | Meeting 1, ~11:38–11:43, ~23:03–23:22 (expected adaptation period: 15 days to 1 month) | M | Stated |
| NFR-16 | Stock levels and reports shall reflect a completed sale within 5 seconds. | Team analysis, based on Meeting 1, ~14:55 (stock should drop on every payment); 5 seconds set by the team | M | Assumed |
| NFR-17 | The POS shall handle at least [N] orders per hour per branch during weekend peaks. | Team analysis, based on Meeting 1, ~18:21 (weekends are the busiest); [N] unknown | M | Assumed |
| NFR-18 | A failure at one branch or of the central server shall not stop order taking and payment at the other branches. | Team analysis, based on Meeting 1, ~10:42–10:53 (today the terminals stop when the main server is down) | M | Assumed |

**Proposed requirements:** FR-15, FR-16, FR-40, NFR-03, NFR-04 (5 of the maximum 6).

## 5. Assumptions and Constraints

| # | Type | Assumption / Constraint | Source |
|---|---|---|---|
| C-01 | Business | Netsis stays as the official accounting system (general ledger, tax, official books). The system exports data to Netsis and does not replace it. | Meeting 1, ~08:24–08:30; approved proposal |
| C-02 | Business | The system replaces KerzzPOS and must keep the KerzzPOS features the client values (detailed revenue and cash reports). | Team decision (approved proposal); Meeting 1, ~07:36–07:43, ~09:36–09:38 |
| C-03 | Legal | Sales receipts in Turkey must be issued through a certified fiscal cash-register device (ÖKC). Connecting a real device is outside this project; the prototype simulates it (FR-40). The rules, including any e-Adisyon obligation, still need to be checked. | Team analysis |
| C-04 | Legal | Venues are inspected by the Ministry of Agriculture and Forestry for food safety. Which records the system must keep for this is unknown (see Open Questions). | Meeting 1, ~19:44–20:15 |
| C-05 | Business | Goods are used within a week or a month and are not stored long, so expiry-date tracking is not required. | Meeting 1, ~20:18–20:32 |
| C-06 | Organisational | Staff are used to the current workflow; the client expects a transition period of 15 days to 1 month. | Meeting 1, ~11:38–11:43, ~23:03–23:22 |
| C-07 | Organisational | The number of active branches changes with the season (4-5 in summer, 3 in winter). | Meeting 1, ~00:26 |
| C-08 | Commercial | The client accepts a model of a setup fee plus a monthly maintenance fee. The client does not want the system to be shut down immediately when a payment is late. | Meeting 1, ~13:36–13:41, ~21:21, ~21:36–21:53 |
| C-09 | Commercial | The client expects remote support at any hour, as with the current provider. | Meeting 1, ~13:56–14:10 |
| C-10 | Business | A previous system (Mobrez) was abandoned because it was too simple and had almost no reports. The new system must not be a simplified tool. | Meeting 1, ~13:01–13:27 |

## 6. Open Questions (for Meeting 2)

**Conflicting or unclear items**

1. Are items transferred between branches? The client answered "no" at ~11:14 and "yes" at ~24:18. (FR-35)
2. Who will enter goods receipts? Warehouse staff receive the goods but "do not enter data" (~22:21). (FR-20)
3. What does "cost integration" mean (~15:06): purchase cost per item, cost per dish, or something else? (FR-36)
4. Which KerzzPOS reports do you use and must keep? Can you share screenshots of the screens (offered at ~07:02)? (FR-07, C-02)
5. Which system is the 30-year-old one?

**Confirming Assumed requirements**

6. Should bartenders and chefs send material requests through the system instead of WhatsApp, with approval by purchasing? (FR-24, FR-25, FR-26)
7. Should goods receipts, delivery-note photos, returns and storage location be recorded in the system? (FR-20 to FR-23)
8. Do you need current-account statements in this system, or only in Netsis? (FR-02)
9. Is one case always converted to a fixed number of bottles per item? (FR-30)
10. Who may see purchase prices, supplier agreements and profit margins? (NFR-02)
11. Is a daily backup with at most 24 hours of data loss acceptable? (NFR-05)
12. How should a sold dish reduce stock: is there a recipe for each menu item, or only items sold as-is (e.g. drinks) in the first version? (FR-29)
13. Which device will be used in the kitchen? (NFR-14)

**Numbers for non-functional requirements**

14. Is a 2% stock difference after a count acceptable? (NFR-07)
15. Is 2 minutes per invoice review acceptable? (NFR-09)
16. Is a 2-hour full count per branch acceptable for weekly counting? (NFR-10)
17. How many orders per hour does a branch take at the weekend peak? (NFR-17)
18. How many staff will actually use the system? (NFR-13)

**Confirming Proposed requirements**

19. Should every extracted invoice be reviewed and approved by a user before it changes stock or accounts? (FR-15, FR-16)
20. Which fiscal cash-register device is used today and how is it connected to KerzzPOS? (FR-40, C-03)
21. Should every user have a personal login? (NFR-03)
22. Should every change to financial and stock records be logged with user and time? (NFR-04)

**Still unknown (not written as requirements)**

23. Which records do food-safety inspections require (expiry dates, cold chain, alcohol licence)? (C-04)
24. In what format can Netsis import data? (FR-14)
25. Are supplier invoices available as e-invoice files as well as PDF?
