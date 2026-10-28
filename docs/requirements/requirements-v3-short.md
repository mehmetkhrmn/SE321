# Requirements Specification (v3, Short Version)

**Project:** [PROJECT NAME]: Restaurant POS with Stock, Invoice and Current-Account Tracking
**Group:** Section 2 - Group 2
**Client:** Mustafa Ulukaya, Financial Director, Rise Group
**Sources:** Meeting 1 = first client meeting, 15/10/2026 (audio recording, ~25:38). Times are approximate positions in the recording.
**Full version:** [requirements-v3.md](requirements-v3.md) (43 FR, 18 NFR). This short version keeps the most important 15 FR and 8 NFR; the "Full v3" column gives the matching ID there.

---

## 1. Project / Problem Summary

Rise Group runs restaurant and bar venues with 4-5 branches in summer and 3 in winter. Today it uses two systems that do not exchange data: KerzzPOS for sales and payments, and Netsis for accounting. Netsis works well; the problems come from KerzzPOS and from the missing link between the two. Sales and purchase data are moved by hand through Excel and entered more than once. Stock figures in KerzzPOS are not accurate, there are no low-stock alerts, and a monthly count takes 4-5 hours. In peak season 70-80 supplier invoices arrive every week and are typed in by hand, which the client calls the biggest problem.

The proposed system replaces KerzzPOS and works with Netsis, which remains the official accounting system. It covers the client's three priorities: (1) current-account and cash records, (2) invoice and delivery-note processing, (3) stock. A POS with core functions only is the place where sales data starts.

## 2. Actors / Stakeholders

| Actor / Stakeholder | Role | Source |
|---|---|---|
| Financial Director (client) | Responsible for accounting and finance; uses reports, current accounts and cash records; final decision maker | Meeting 1, ~00:12, ~22:10 |
| Purchasing Manager | Approves requests, orders from suppliers, enters invoice and stock data | Meeting 1, ~00:47, ~03:04, ~22:02–22:08 |
| Warehouse Staff | Receives and stores goods from suppliers | Meeting 1, ~04:11–04:59, ~22:18–22:21 |
| Chef and Bartender | Request kitchen and bar materials | Meeting 1, ~02:56–02:59 |
| Waiter | Takes table orders and payments at the POS | Meeting 1, ~00:57 |
| Suppliers | Deliver goods with delivery notes and send invoices | Meeting 1, ~04:40–04:47, ~18:38 |
| Netsis (external system) | Official accounting system; receives exported data | Meeting 1, ~03:45, ~08:24–08:30 |

## 3. Functional Requirements

Priority: **H** = part of the client's top three (current account/cash, invoice/delivery note, stock) or called the biggest problem; **M** = asked for or described as a problem, but not in the top three; **L** = client said "would be nice" or mentioned it in passing.

| ID | Requirement | Source / Evidence | Priority | Status | Full v3 |
|---|---|---|---|---|---|
| FR-01 | The system shall record current-account transactions. | Meeting 1, ~24:39, ~25:01 | H | Stated | FR-01 |
| FR-02 | The system shall record cash-register entries (money in) and exits (money out). | Meeting 1, ~14:30, ~25:01 | H | Stated | FR-03 |
| FR-03 | The system shall produce an end-of-day cash report showing cash total, credit-card total, entries and exits. | Meeting 1, ~14:17–14:36 | H | Stated | FR-05 |
| FR-04 | The system shall produce revenue reports for a selected period. | Meeting 1, ~09:20–09:38 (named as a feature to keep) | H | Stated | FR-06 |
| FR-05 | The system shall automatically extract the supplier, line items, quantities, unit prices and discounts from a supplier invoice uploaded as a PDF file. | Meeting 1, ~01:13–01:32, ~18:38, ~19:22–19:32 | H | Stated | FR-10, FR-11 |
| FR-06 | The system shall require a user to review and approve extracted invoice data before it changes stock or current-account records. | Team proposal: extracted data changes financial and stock records, and extraction can be wrong (instructor feedback on the proposal also recommended a human verification step) | H | Proposed | FR-15 |
| FR-07 | The system shall export approved invoice data to Netsis. | Meeting 1, ~01:32, ~02:25 | H | Stated | FR-14 |
| FR-08 | The system shall record delivery notes received from suppliers. | Meeting 1, ~25:06 | H | Stated | FR-19 |
| FR-09 | The system shall keep the stock quantity of each item for each branch. | Meeting 1, ~25:06, ~00:26 | H | Stated | FR-28 |
| FR-10 | The system shall add the items of an approved purchase invoice to stock. | Team analysis, based on Meeting 1, ~02:22, ~06:19–06:37 (stock is fed by purchase invoices in KerzzPOS today) | H | Assumed | FR-17 |
| FR-11 | The system shall reduce stock by the items of an order when its payment is completed. | Meeting 1, ~14:39–14:55 | H | Stated | FR-29 |
| FR-12 | The system shall alert users when the stock of an item falls below the critical level set for that item. | Meeting 1, ~03:09–03:18 (example: soft drinks below 50) | M | Stated | FR-32, FR-33 |
| FR-13 | The system shall support a stock count for a branch and record the difference between counted and recorded quantities. | Meeting 1, ~08:51, ~17:31–17:39 | M | Stated | FR-34 |
| FR-14 | The system shall keep a separate order for each table, listing the ordered items. | Team analysis, based on Meeting 1, ~14:48–14:53 and the team decision to replace KerzzPOS | H | Assumed | FR-37 |
| FR-15 | The system shall record the payment of each order as cash or credit card. | Meeting 1, ~14:30 | H | Stated | FR-04, FR-39 |

## 4. Non-Functional Requirements

| ID | Category | Requirement | Source / Evidence | Priority | Status | Full v3 |
|---|---|---|---|---|---|---|
| NFR-01 | Security | The system shall show purchase prices, supplier agreements and profit margins only to the roles the client authorises. | Meeting 1, ~19:01–19:19 (team asked; client did not clearly confirm) | H | Assumed | NFR-02 |
| NFR-02 | Security | The system shall require each user to log in with a personal account before any function is available. | Team proposal: the system holds financial data and is used by many staff roles | H | Proposed | NFR-03 |
| NFR-03 | Security | The system shall log every change to invoices, cash, current-account and stock records with the user, time, old value and new value. | Team proposal: financial and stock records must be traceable | H | Proposed | NFR-04 |
| NFR-04 | Reliability | The system shall back up its data at least once a day, so that no more than 24 hours of data can be lost. | Meeting 1, ~09:48–09:57 (backup came up as an example; client's answer unclear); numbers set by the team | M | Assumed | NFR-05 |
| NFR-05 | Performance | The system shall handle at least 80 supplier invoices per week. | Meeting 1, ~18:33–18:56 (70-80 per week in peak season) | H | Stated | NFR-08 |
| NFR-06 | Performance | Stock levels and reports shall reflect a completed sale within 5 seconds. | Team analysis, based on Meeting 1, ~14:55 (stock should drop on every payment); 5 seconds set by the team | M | Assumed | NFR-16 |
| NFR-07 | Usability | Staff shall be able to carry out their core tasks in the system without help within 30 days of training. | Meeting 1, ~11:38–11:43, ~23:03–23:22 (expected adaptation period: 15 days to 1 month) | M | Stated | NFR-15 |
| NFR-08 | Portability | The system shall be usable from a mobile phone and from an office computer. | Meeting 1, ~16:59–17:05 | M | Stated | NFR-14 |

**Categories covered:** Security, Reliability, Performance, Usability, Portability.
**Proposed requirements:** FR-06, NFR-02, NFR-03 (3 of the maximum 6).

## 5. Assumptions and Constraints

| # | Type | Assumption / Constraint | Source |
|---|---|---|---|
| C-01 | Business | Netsis stays as the official accounting system (general ledger, tax, official books). The system exports data to Netsis and does not replace it. | Meeting 1, ~08:24–08:30; approved proposal |
| C-02 | Business | The system replaces KerzzPOS and must keep the KerzzPOS features the client values (detailed revenue and cash reports). | Team decision (approved proposal); Meeting 1, ~07:36–07:43, ~09:36–09:38 |
| C-03 | Legal | Sales receipts in Turkey must be issued through a certified fiscal cash-register device (ÖKC). Connecting a real device is outside this project; the prototype simulates it. The rules still need to be checked. | Team analysis |
| C-04 | Legal | Venues are inspected by the Ministry of Agriculture and Forestry for food safety; which records the system must keep for this is unknown. | Meeting 1, ~19:44–20:15 |
| C-05 | Organisational | The number of active branches changes with the season (4-5 in summer, 3 in winter). | Meeting 1, ~00:26 |
| C-06 | Organisational | Staff are used to the current workflow; the client expects a transition period of 15 days to 1 month. | Meeting 1, ~11:38–11:43, ~23:03–23:22 |

## 6. Open Questions (for Meeting 2)

1. Which KerzzPOS reports do you use and must keep? Can you share screenshots of the screens (offered at ~07:02)? (FR-04, C-02)
2. How should a sold dish reduce stock: is there a recipe for each menu item, or only items sold as-is (e.g. drinks) in the first version? (FR-11)
3. Who may see purchase prices, supplier agreements and profit margins? (NFR-01)
4. Is a daily backup with at most 24 hours of data loss acceptable? (NFR-04)
5. Is a 5-second update of stock and reports after a sale acceptable? (NFR-06)
6. Should every extracted invoice be reviewed and approved by a user before it changes stock or accounts? (FR-06)
7. Should every user have a personal login? (NFR-02)
8. Should every change to financial and stock records be logged with user and time? (NFR-03)
9. Which fiscal cash-register device is used today and how is it connected to KerzzPOS? (C-03)
10. Are items transferred between branches? The client answered "no" at ~11:14 and "yes" at ~24:18.
11. In what format can Netsis import data? (FR-07)
12. Which records do food-safety inspections require (expiry dates, cold chain, alcohol licence)? (C-04)
