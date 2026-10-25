# SE 305 / SE 321 Software Specification and Design: Project Proposal

> Teslim edilecek kısa versiyon. Öğrenci numaraları ve e-postalar repo public olduğu için burada yok; teslim edilen belgede v1'deki gibi kalacak. Ayrıntılı taslak: [proposal-v2-detayli.md](proposal-v2-detayli.md).

| | |
|---|---|
| **Project Name** | **[PROJECT NAME]**: Stock, Invoice and Current-Account Tracking for Multi-Branch Restaurants |
| **Section / Group No.** | Section 2 - Group 2 |
| **Proposal Date** | 18/10/2026 |
| **Group Members** | Mehmet Kahraman, İsmail Yiğit Şendur, Hakkı Can Duran, Hüseyin Esen, Batuhan Deliaslan, Umutcan Yavuz, Erden Can Aktan |
| **Client** | Mustafa Ulukaya, Financial Director, Rise Group |
| **First Meeting Date** | 15/10/2026 |

---

## Problem Identified with the Client

Rise Group runs restaurant and bar venues: 4-5 branches in summer and 3 in winter. Stock moves through a chain of roles. The chef and the bartender post their weekly needs in a WhatsApp group. The purchasing manager approves them and orders from suppliers. Warehouse staff receive the goods at the door against a signed delivery note. The purchasing manager then enters the invoices.

The business uses two systems that do not exchange data. **KerzzPOS** handles sales and payments. **Netsis** handles accounting and works well; the client does not see it as the problem. The problems are in the work between them:

- **Invoices are processed by hand.** The client called this the biggest problem. In peak season 70-80 supplier invoices arrive every week, each with its own prices and discounts, and each is typed in manually.
- **Data is entered twice.** Purchase and sales data are re-entered across KerzzPOS, Excel and Netsis, which causes mismatches.
- **Stock is unreliable.** Stock figures in KerzzPOS are not accurate, there are no low-stock alerts, and a monthly count takes 4-5 hours.

The client's priorities are, in order: **(1) current-account and cash records, (2) invoice and delivery-note processing, (3) stock.**

## Proposed Software Solution

We propose a system that works **alongside** KerzzPOS and Netsis rather than replacing them. KerzzPOS remains the point of sale and Netsis remains the official accounting system. Our system covers the three priorities:

1. **Current-account and cash records (pre-accounting).** Supplier invoices and payments, payment due dates, and daily cash and card totals per branch. Approved records are prepared for transfer to Netsis. General ledger, tax and payroll stay in Netsis.
2. **Invoice and delivery-note processing.** Users upload supplier invoices and delivery notes as PDF, e-invoice files or photos. The system extracts the supplier, document number, date, line items, quantities, prices, discounts, VAT and totals. Uncertain or inconsistent values are highlighted, and **a user checks and approves every document**. Only approved documents change stock or current-account records.
3. **Stock.** Item records with unit conversion (e.g. case to bottle), stock entry from approved delivery notes, stock reduction from the daily KerzzPOS sales report (starting with items sold as-is, such as drinks), stock counts per branch, and low-stock alerts (e.g. soft drinks below 50 units).

Data is exchanged with KerzzPOS and Netsis through their existing report exports and import files; the exact formats will be confirmed with the client.

Users are the financial director, the purchasing manager, warehouse staff, chefs and bar staff, each with role-based access. Purchase prices and financial data are visible only to authorized roles. All changes to financial and stock records are logged, and data is backed up daily. Specific, measurable requirements for security and data timeliness will be defined in the requirements stage.

## Meeting Photo with the Client

[v1'deki fotoğraf]
