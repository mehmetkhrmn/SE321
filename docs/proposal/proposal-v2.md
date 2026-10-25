# SE 305 / SE 321 Software Specification and Design: Project Proposal

> Teslim edilecek kısa versiyon. Öğrenci numaraları ve e-postalar repo public olduğu için burada yok; teslim edilen belgede v1'deki gibi kalacak. Ayrıntılı taslak: [proposal-v2-detayli.md](proposal-v2-detayli.md).

| | |
|---|---|
| **Project Name** | **[PROJECT NAME]**: Restaurant POS with Stock, Invoice and Current-Account Tracking |
| **Section / Group No.** | Section 2 - Group 2 |
| **Proposal Date** | 18/10/2026 |
| **Group Members** | Mehmet Kahraman, İsmail Yiğit Şendur, Hakkı Can Duran, Hüseyin Esen, Batuhan Deliaslan, Umutcan Yavuz, Erden Can Aktan |
| **Client** | Mustafa Ulukaya, Financial Director, Rise Group |
| **First Meeting Date** | 15/10/2026 |

---

## Problem Identified with the Client

Rise Group runs restaurant and bar venues with 4-5 branches in summer and 3 in winter. Stock moves through a chain of roles: the chef and the bartender post their weekly needs in a WhatsApp group, the purchasing manager approves them and orders from suppliers, warehouse staff receive the goods against a signed delivery note, and the purchasing manager then enters the invoices.

The business relies on two disconnected systems. KerzzPOS handles sales and payments, and Netsis handles accounting. Netsis works well and the client does not see it as the problem; the problems come from KerzzPOS and from the missing link between the two systems. Because there is no automated data flow, staff move data by hand through Excel and enter the same information more than once. Stock is tracked in KerzzPOS, but its figures are not accurate, there are no low-stock alerts, and a single monthly count takes 4-5 hours. During peak season 70-80 supplier invoices arrive every week, each with its own prices and discounts, and the client calls entering them by hand the biggest problem. The client also considers the security of the current POS weak. Finally, stock and cash figures for all branches cannot be seen in one place, which makes management harder.

The client's priorities are, in order: (1) current-account and cash records, (2) invoice and delivery-note processing, and (3) stock.

## Proposed Software Solution

We propose a single system that **replaces KerzzPOS** and **works with Netsis**, which stays as the official accounting system. Because sales are recorded in our own POS, sales, stock, invoices and cash are kept in one place. The business then works with two connected systems instead of two disconnected systems plus Excel. The system covers the client's three priorities, with the POS as the place where sales data starts:

1. **Current-account and cash records (pre-accounting).** Daily cash and card totals per branch, taken directly from POS sales. Supplier invoices, payments and payment due dates. Approved records are exported to Netsis through its import files. General ledger, tax and payroll stay in Netsis.
2. **Invoice and delivery-note processing.** Users upload supplier invoices and delivery notes as PDF, e-invoice files or photos. The system extracts the supplier, document number, date, line items, quantities, prices, discounts, VAT and totals. Uncertain or inconsistent values are highlighted, and **a user checks and approves every document**. Only approved documents change stock or current-account records.
3. **Stock.** Item records with unit conversion (e.g. case to bottle), stock entry from approved delivery notes, automatic stock reduction on each POS sale (starting with items sold as-is, such as drinks), stock counts per branch, and low-stock alerts (e.g. soft drinks below 50 units).
4. **POS (core functions only).** Menu items and prices, table orders, and payment by cash or card. It keeps what the client values most in KerzzPOS: detailed daily revenue and cash reports per branch. Reservations, online ordering and loyalty programs are out of scope.

Users are the financial director, the purchasing manager, warehouse staff, chefs, bar staff and waiters, each with role-based access. Purchase prices and financial data are visible only to authorized roles. All changes to sales, financial and stock records are logged, and data is backed up daily. Specific, measurable requirements for security and data timeliness will be defined in the requirements stage.

## Meeting Photo with the Client

[v1'deki fotoğraf]
