# 📄 **Sales Order (SO) Module – Functional Documentation**

---

## 1. Module Overview

The **Sales Order Module** is the point where the entire manufacturing and delivery workflow begins.
When a customer places an order, the system creates a **Sales Order (SO)** containing product, quantity, pricing, and delivery timelines. Based on this order, the system triggers:

* Inventory stock verification
* Production process (if material available / partially available)
* Purchase procurement process (if material not available)
* Quality, Packaging, and Dispatch steps

This module ensures that every order is traceable, process-driven, and completed with minimal manual intervention.

---

## 2. Objective & Purpose of the SO Module

| Objective                                                    | Purpose                                        |
| ------------------------------------------------------------ | ---------------------------------------------- |
| Record customer demand accurately                            | Avoid data loss, confusion, manual tracking    |
| Provide real-time order status                               | End-to-end visibility for management           |
| Trigger material planning                                    | Prevent production delays                      |
| Connect Sales → Inventory → Purchase → Production → Dispatch | Full workflow automation                       |
| Increase delivery speed                                      | Reduce waiting time & over-dependence on teams |

---

## 3. Core Functional Capabilities

| Feature                       | Description                                       |
| ----------------------------- | ------------------------------------------------- |
| Create New Sales Order        | Add customer, item, quantity, timeline, price     |
| Auto Stock Availability Check | System verifies material availability instantly   |
| Order Revision & Terms        | Edit terms before approval                        |
| Approval Workflow (optional)  | Manager approval for high-value orders            |
| Forecasting Insights          | Predict production load & purchase requirements   |
| Order Tracking Dashboard      | Monitoring of pending, completed & in-progress SO |

---

## 4. Inputs Required for Sales Order Creation

🔗 = Linked / dependent on other ERP modules

| Field                             | Description                            | Module Connected          |
| --------------------------------- | -------------------------------------- | ------------------------- |
| 🔗 Customer Name & ID             | Customer selected from master database | Customer Master Module    |
| 🔗 Customer Address & GST Details | Auto-filled from customer master       | Customer Master / Finance |
| 🔗 Product / Item Name            | Item pulled from SKU master list       | Item Master / Inventory   |
| Required Quantity                 | No. of units required                  | —                         |
| Delivery Due Date                 | Requested commitment date              | —                         |
| 🔗 Price / Discount / Tax         | Derived from pricing master            | Pricing Master / Finance  |
| Custom Notes                      | Packaging/quality instructions         | —                         |

---

## 5. Output Records Generated After SO Creation

| Output                             | Purpose                                   | Module Triggered             |
| ---------------------------------- | ----------------------------------------- | ---------------------------- |
| Sales Order Number                 | Unique reference ID                       | Sales Module                 |
| Stock Requirement Report           | Shows available vs required stock         | 🔗 Inventory Module          |
| Purchase Requisition (If required) | Auto-triggered when stock is insufficient | 🔗 Purchase Module           |
| Work Order for Production          | Issued for manufacturing if stock exists  | 🔗 Manufacturing Module         |               |
| Invoice & Shipping Document        | Final export for customer dispatch        | 🔗 Billing + Dispatch Module |

---

## 6. Sales Order Business Flow

```text
Customer Order Received
        ↓
Create Sales Order
        ↓
Check Material Availability
        ├── Material Available → Manufacturing → QA → Packaging → Dispatch + Invoice
        ↓
        └── Material Not Available → Purchase Order → GRN Received → QA → Manufacturing → Dispatch
```

This ensures continuous flow without manual follow-ups.

---

## 7. Internal Workflow Breakdown

### Phase 1 – Order Intake

1. Customer contacts sales team
2. SO is created with required details
3. SO is saved and assigned unique SO number

### Phase 2 – Material Availability Validation

* System checks stock in warehouse
* If stock is present → Production is allocated
* If stock is insufficient → Purchase Order is initiated

### Phase 3 – Production & Quality

* Review Bill of Materials
* Raw material consumed → Production initiated
* QA approval mandatory before packaging

### Phase 4 – Dispatch & Invoicing

* Packed goods scheduled for shipping
* Invoice generated and sent to customer
* Order marked as **Closed / Completed**

---

## 8. UI/Screen Structure (Future Implementation Layout)

Even though UI is not developed yet, this structure can be followed:

### 🖥️ Sales Order Entry Screen Elements

| Section              | Fields Included                         |
| -------------------- | --------------------------------------- |
| Customer Information | Customer ID 🔗, Name 🔗, Address 🔗     |
| Order Details        | SKU 🔗, Quantity, UOM 🔗, Delivery Date |
| Pricing Panel        | Rate 🔗, Discount %, Tax %, Final Value |
| Internal Note Box    | Handling requests, QA instructions      |
| Action Buttons       | Save, Submit, Update, Cancel            |

*A color-coded layout may be added later for client visibility.*

---

## 9. Exception Handling (Edge Cases)

| Condition                | System Action                                      |
| ------------------------ | -------------------------------------------------- |
| Wrong item code selected | Pop-up alert → Data validation                     |
| Insufficient stock       | Auto Purchase Request → Purchase Team Notification |
| Delivery overdue         | Order highlighted in red alerts                    |
| QA failure               | Material returned or re-process triggered          |

---