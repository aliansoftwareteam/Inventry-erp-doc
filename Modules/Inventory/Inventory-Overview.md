# 📦 **Stock (Inventory) – Overview Document**

---

## **1. Items Catalogue**

Master data used to define all items and product structures.

| Feature               | Description                                                                                                                                                 |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Item**              | The core master record representing products, raw materials, consumables, and services. Contains item details, pricing, defaults, and inventory properties. |
| **Item Group**        | Categorizes items for reporting, pricing rules, and grouping. Helps in analytics and filtering.                                                             |
| **Product Bundle**    | A combination of multiple items sold as a single packaged product. Useful for gift sets, kits, or combo offers.                                             |
| **Item Alternative**  | Maintains substitute items that can be used when the primary item is unavailable.                                                                           |
| **Item Manufacturer** | Stores manufacturer details linked to items, useful for vendor management and traceability.                                                                 |

---

## **2. Stock Transactions**

Documents that create actual stock movement and update inventory levels.

| Transaction          | Description                                                                                                               |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| **Material Request** | A request to procure, transfer, or manufacture materials. Often used by production, stores, or departments needing stock. |
| **Stock Entry**      | Internal stock transfers or adjustments such as repack, manufacture entry, material issue, or scrap entry.                |
| **Delivery Note**    | Records the dispatch of goods to customers or project sites, reducing stock.                                              |
| **Purchase Receipt** | Captures the physical receipt of goods from suppliers, increasing stock.                                                  |
| **Pick List**        | Guides warehouse staff on which items and stock locations to pick for delivery or production orders.                      |
| **Delivery Trip**    | Manages and tracks vehicle trips used for delivering multiple delivery notes.                                             |

---

## **3. Reports**

All analytical and operational reports related to stock levels, movements, and performance.

### **Stock Reports**

| Report                           | Description                                                                              |
| -------------------------------- | ---------------------------------------------------------------------------------------- |
| **Stock Ledger**                 | Full transaction-wise movement of stock including quantities, warehouses, and valuation. |
| **Stock Balance**                | Real-time available stock across warehouses.                                             |
| **Stock Projected Qty**          | Future stock projection including reserved, ordered, and planned quantities.             |
| **Stock Summary**                | Consolidated summary of quantities, value, and stock movement.                           |
| **Stock Ageing**                 | Shows how long an item has been in inventory; helps identify slow-moving items.          |
| **Item Price Stock**             | Displays stock valuation and item pricing details.                                       |
| **Warehouse Wise Stock Balance** | Shows stock quantity distributed across each warehouse or location.                      |

---

## **4. Settings**

Configuration tools to define how inventory behaves across the system.

| Setting                   | Description                                                                                      |
| ------------------------- | ------------------------------------------------------------------------------------------------ |
| **Stock Settings**        | Global configuration for stock valuation method, auto-reorder, posting rules, and item behavior. |
| **Warehouse**             | Creation and management of storage locations, warehouses, and hierarchical warehouse structure.  |
| **Unit of Measure (UOM)** | Defines measurement units (kg, box, pcs), controlling conversions and transaction validity.      |
| **Item Variant Settings** | Controls attribute-based item variant creation (size, color, grade).                             |
| **Brand**                 | Categorization of items by brand for reporting and filtering.                                    |
| **Item Attribute**        | Defines item characteristics used for generating item variants.                                  |
| **UOM Conversion Factor** | Maintains conversion rules between units (e.g., 1 box = 12 pieces).                              |

---

## **5. Serial No and Batch**

Used for traceability and lifecycle tracking of serialized or batch-managed products.

| Feature       | Description                                                                                                                 |
| ------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **Serial No** | Unique identification for items tracked individually (e.g., electronics, machines). Includes warranty and delivery history. |
| **Batch**     | Group of items produced or received together with shared properties like expiry or manufacture date.                        |

---

## **6. Tools**

Utilities to maintain, adjust, and audit the inventory.

| Tool                     | Description                                                                                |
| ------------------------ | ------------------------------------------------------------------------------------------ |
| **Stock Reconciliation** | Adjusts system stock levels to match physical counts. Used during audits or corrections.   |
| **Quick Stock Balance**  | Instantly view available stock for selected items/warehouses without running full reports. |

---