# ERP System for F&B Chain — Highlands Coffee (Flectra ERP)

Business Analysis & ERP functional configuration project simulating an end-to-end
supply chain and outlet management solution for a coffee-chain retailer, built on
**Flectra ERP** (Odoo-based open-source ERP).

> Academic project — Enterprise Resource Planning course.
> This repo documents the business analysis work, ERP configuration, and UAT results.

---

## 📌 My Role
**Business Analyst & Functional Consultant**
- Analyzed AS-IS supply chain and outlet operations
- Documented business logic via BPMN (AS-IS / TO-BE)
- Configured Flectra Inventory, Purchase, POS, and BOM modules
- Designed and executed the UAT test plan

---

## 🏢 Business Context

Highlands Coffee is a nationwide coffee-chain retailer (1,000+ outlets in reality)
operating a closed-loop supply chain — from raw material sourcing and in-house
roasting to distribution across outlets — organized into 3 regional branches
(North / Central / South).

### Key pain points identified (AS-IS)
| Area | Problem |
|---|---|
| **Supply chain visibility** | No real-time data link between outlets and the central warehouse; stock counted manually and requested via Excel/Zalo, causing a bullwhip effect and stockouts during peak hours |
| **BOM & wastage control** | POS was not linked to a Bill of Materials — selling a drink recorded revenue only, without auto-deducting the coffee beans/milk consumed, so wastage and theft went untracked |
| **Financial reconciliation** | Revenue from multiple channels (in-store, app, GrabFood, ShopeeFood, VNPay, MoMo) had to be manually reconciled into accounting, delaying P&L visibility |
| **Procurement paperwork** | Purchase orders, delivery notes, and invoices were matched manually across 3 paper documents (Order – Receipt – Invoice) |

---

## 🎯 Solution Scope (TO-BE, simulated in Flectra)

- **Warehouse structure:** 1 central warehouse (HQ) + 4 outlet warehouses
  (Đinh Tiên Hoàng, Bưu Điện Thành Phố, Landmark 81, Diamond Plaza), each split
  into Stock / Shelf / Scrap sub-locations
- **Multi-company setup** across 3 regional branches (North / Central / South)
- **BOM (Bill of Materials)** for beverage recipes → automatic ingredient-level
  inventory deduction at POS checkout
- **Automated Reordering Rules** and internal transfer protocols between HQ and outlets
- **FIFO-based perishable inventory** management for fresh ingredients
- Modules configured: **Sales, POS, Inventory, Purchase, Invoicing, BOM**

---

## ✅ UAT Results

Executed **20 UAT test cases** covering the full P2P and O2C cycles:

- Sales order creation & fulfillment (Website + POS)
- POS session open/close, returns, credit notes, promotions
- Purchase order → goods receipt → vendor bill → payment
- Internal transfers between HQ and outlet warehouses
- Reordering rules (automated replenishment)
- **BOM setup for beverage recipes** (TC14 — core to solving the wastage problem above)

**Result: 20/20 test cases passed (100% pass rate)**

| # | Test Case | Result |
|---|---|---|
| TC01–TC08 | Sales, POS session, invoicing & payment | Pass |
| TC09–TC11 | Internal transfer, forecast report, reordering rules | Pass |
| TC12–TC13 | Vendor bill & payment | Pass |
| **TC14** | **BOM setup for beverage recipes** | **Pass** |
| TC15–TC20 | Loyalty, returns, credit notes, pricelist, cancellation, scrap | Pass |

---

## 🛠 Tech Stack

`Flectra ERP` · `PostgreSQL` · `BPMN` · `Excel` (data migration templates)

---

## 📁 Repo Contents

- `/diagrams` — AS-IS / TO-BE BPMN process diagrams, org chart
- `/uat` — Full UAT test case documentation
- `/screenshots` — Flectra configuration screenshots (warehouses, BOM, reordering rules, POS)
- `/docs` — Full project report (business analysis, gap analysis, configuration guide)

---

## 📈 Outcome

The proposed solution directly addresses the AS-IS pain points: real-time
stock visibility between outlets and HQ, automatic ingredient-level deduction
via BOM to control wastage, and a unified data flow to speed up financial
reconciliation across sales channels.
