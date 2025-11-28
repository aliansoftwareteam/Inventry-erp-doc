# 🟧 **1. Sales**

| **Subsection**     | **Description**                                        |
| ------------------ | ------------------------------------------------------ |
| Inquiry Management | Record incoming customer inquiries.                    |
| Quotation          | Create and send quotations; convert to Sales Order.    |
| Sales Order (SO)   | Confirm customer orders and trigger stock/production.  |
| Order Approval     | Workflow for approval of special pricing or discounts. |
| Sales Return       | Manage goods returned by customers.                    |
| Sales Reports      | Party-wise, item-wise, pending order summaries.        |

---

# 🟨 **2. Inventory / Material Management**

| **Subsection**          | **Description**                                      |
| ----------------------- | ---------------------------------------------------- |
| Stock Check (Real-Time) | Auto-check availability during Sales Order creation. |
| Goods Receipt (GRN)     | Add received materials into inventory.               |
| Material Issue/Return   | Issue materials to production; return unused items.  |
| Warehouse Management    | Multi-location, rack, bin stock tracking.            |
| Stock Adjustment        | Fix mismatches or damaged stock.                     |
| Reorder Alerts          | Low-stock alerts for reordering.                     |
| Inventory Reports       | Stock summary, valuation, ageing.                    |

---

# 🟩 **3. Purchase**

| **Subsection**            | **Description**                               |
| ------------------------- | --------------------------------------------- |
| Purchase Requisition (PR) | Auto-created when stock is insufficient.      |
| Vendor Selection          | Select supplier from Party Master.            |
| Purchase Order (PO)       | Create and manage purchase orders.            |
| Material Receipt (GRN)    | Receive goods and update stock.               |
| Purchase Invoice          | Record vendor invoice.                        |
| Purchase Return           | Return rejected or incorrect goods.           |
| Purchase Reports          | Pending PO list, vendor performance analysis. |

---

# 🟥 **4. Manufacturing / Production**

| **Subsection**                | **Description**                               |
| ----------------------------- | --------------------------------------------- |
| Work Order (WO)               | Production order created from Sales Order.    |
| Bill of Materials (BOM)       | Define raw materials needed for production.   |
| Routing / Job Card            | Define production steps and machine workflow. |
| Material Issue for Production | Issue raw materials for manufacturing.        |
| WIP Tracking                  | Monitor work-in-progress stages.              |
| Scrap / Rework                | Record scrap or reprocessed work.             |
| Production Completion         | Transfer finished goods to inventory.         |

---

# 🟪 **5. Quality Control**

| **Subsection**        | **Description**                                |
| --------------------- | ---------------------------------------------- |
| Incoming QC (IQC)     | Inspect quality of purchased materials.        |
| In-Process QC (IPQC)  | Quality checks during manufacturing.           |
| Final QC (FQC)        | Inspect finished goods before packaging.       |
| QC Rejection Handling | Rework, scrap, or return-to-vendor processing. |
| QC Reports            | Defects, inspection history, approval trends.  |

---

# 🟫 **6. Packaging**

| **Subsection**         | **Description**                                   |
| ---------------------- | ------------------------------------------------- |
| Packaging Execution    | Pack finished goods with labels & units.          |
| Packaging QC           | Final inspection of packed goods (weight/labels). |
| Batch / Lot Management | Generate batch or lot numbers.                    |
| Packing List           | Create packing slips for dispatch.                |

---

# 🟦 **7. Dispatch & Logistics**

| **Subsection**        | **Description**                           |
| --------------------- | ----------------------------------------- |
| Dispatch Planning     | Plan shipments for Sales Orders.          |
| Delivery Challan (DC) | Document for dispatching goods.           |
| Transport Management  | Vehicle, driver, transporter details.     |
| Gate Pass             | Authorization for goods leaving premises. |
| Shipment Tracking     | Delivered vs pending dispatch tracking.   |

---

# 🟧 **8. Finance & Billing**

| **Subsection**                 | **Description**                                  |
| ------------------------------ | ------------------------------------------------ |
| Sales Invoice                  | Invoice generation after dispatch.               |
| Purchase Invoice               | Vendor invoice entry.                            |
| Unified Party Ledger           | One ledger for customer/vendor/both.             |
| Auto Netting-Off               | Auto-adjust payable & receivable for same party. |
| Payment Receipt / Payment Made | Record money received or paid.                   |
| Credit/Debit Notes             | Adjustments for returns, rate changes.           |
| Tax Management (GST)           | GST/HSN calculations & reports.                  |

---

# 🟩 **9. Master Data (Updated with Unified Party Master)**

| **Subsection**                              | **Description**                             |
| ------------------------------------------- | ------------------------------------------- |
| **Party Master (Customer / Vendor / Both)** | Single master for all business partners.    |
| Item Master                                 | Raw materials, products, specifications.    |
| Warehouse Master                            | Warehouse, rack, bin structure.             |
| UOM Master                                  | Unit of measurement definitions.            |
| Tax Master                                  | GST %, tax groups, HSN codes.               |
| BOM Master                                  | Bill of Materials templates.                |
| Price List Master                           | Pricing for parties (customer/vendor/both). |

---

# 🛠 **10. Administration & Security**

| **Subsection**         | **Description**                           |
| ---------------------- | ----------------------------------------- |
| User Management        | Create & manage system users.             |
| Role & Permissions     | Access control for all sections.          |
| Workflow Builder       | Approvals for SO, PO, invoices.           |
| Activity Logs          | Track user operations & changes.          |
| Notifications & Alerts | Stock alerts, approvals, dispatch alerts. |

---
