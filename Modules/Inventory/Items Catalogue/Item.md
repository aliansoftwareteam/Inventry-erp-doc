# 📘 **Item – Detailed Documentation**

The **Item Master** is the core foundation of the Stock (Inventory) module. Every raw material, component, finished good, consumable, service, or non-stock item in the system is defined here.
The item master controls how an item behaves across **Purchasing, Sales, Inventory, Manufacturing, and Quality** modules.

---

# **1. Purpose of Item Master**

The item master is used to:

* Define all products used in buying, selling, manufacturing, and stock operations.
* Store key attributes like item type, UOM, valuations, pricing, and warehouse defaults.
* Control item behavior in stock transactions (batch/serial, expiry, manufacturing, quality checks).
* Maintain item-specific rules such as reorder levels, inspection requirements, and costing method.
* Serve as a centralized reference for all reporting and analytics.

---

# **2. Types of Items**

The system typically supports the following item types:

| Item Type               | Usage                                                                                  |
| ----------------------- | -------------------------------------------------------------------------------------- |
| **Stock Item**          | An item that maintains quantity in inventory (raw material, component, finished good). |
| **Non-Stock Item**      | Does not track inventory (software license, services, fees, transportation).           |
| **Service**             | Used for sales or purchase of services.                                                |
| **Product Bundle Item** | Group of items sold as one unit.                                                       |
| **Variant Item**        | Item created from attributes (size, color, material).                                  |

---

# **3. Item Master Sections & Detailed Fields**

Below is a complete explanation of the standard sections and fields available in the Item master.

---

## **3.1 Basic Information**

| Field                             | Description                                                                  |
| --------------------------------- | ---------------------------------------------------------------------------- |
| **Item Code**                     | Unique identifier for the item. Can be system-generated or manually created. |
| **Item Name**                     | Human-readable name used in transactions and reports.                        |
| **Item Group**                    | Categorization for reporting, pricing, and analytics.                        |
| **Is Stock Item**                 | If enabled, the item maintains stock quantity and valuation.                 |
| **Item Type**                     | Controls operational behavior (Stock, Non-stock, Service).                   |
| **Default Unit of Measure (UOM)** | Base unit like pcs, kg, box.                                                 |

---

## **3.2 Item Description & Details**

| Field                     | Description                                              |
| ------------------------- | -------------------------------------------------------- |
| **Description**           | Detailed description shown in transactions.              |
| **Brand**                 | Used for categorization and reporting.                   |
| **Manufacturer**          | Who manufactures the item.                               |
| **Manufacturer Part No.** | External part number from manufacturer/vendor.           |
| **Item Image**            | Product image used in sales, e-commerce, and quotations. |

---

## **3.3 Inventory Settings**

These settings directly impact stock control, valuation, reordering, and warehouse behavior.

### **Tracking & Identity**

| Field               | Description                                                          |
| ------------------- | -------------------------------------------------------------------- |
| **Has Batch No**    | Enables batch-wise tracking with expiry dates.                       |
| **Has Serial No**   | Enables unique serial-wise tracking for high-value or tracked items. |
| **Warranty Period** | Default warranty given for serialized items.                         |
| **Maintain Stock?** | If disabled, item will not update stock (non-stock item).            |

### **Valuation & Costing**

| Field                     | Description                                             |
| ------------------------- | ------------------------------------------------------- |
| **Valuation Method**      | FIFO / Moving Average (system-wide or item-specific).   |
| **Opening Stock**         | Initial stock quantity during system setup.             |
| **Standard Buying Rate**  | Default purchase rate used for valuation or planning.   |
| **Standard Selling Rate** | Default sales rate used in quotations and sales orders. |

### **Warehouse Defaults**

| Field                 | Description                                                  |
| --------------------- | ------------------------------------------------------------ |
| **Default Warehouse** | Preferred warehouse for storing this item.                   |
| **Reorder Level**     | Minimum quantity at which item should trigger replenishment. |
| **Reorder Qty**       | Quantity to request when reorder level is reached.           |

---

## **3.4 Sales, Purchase Settings**

### **Sales Settings**

| Field                  | Description                                               |
| ---------------------- | --------------------------------------------------------- |
| **Is Sales Item**      | Item can be sold.                                         |
| **Selling Price List** | Default price list or rate.                               |
| **Sales Taxes**        | Item-specific tax template applied in sales transactions. |

### **Purchase Settings**

| Field                  | Description                                |
| ---------------------- | ------------------------------------------ |
| **Is Purchase Item**   | Item can be procured from suppliers.       |
| **Last Purchase Rate** | Auto-updated from purchase transactions.   |
| **Default Supplier**   | Preferred vendor for procurement.          |
| **Purchase Taxes**     | Item-specific tax template for purchasing. |

## **3.5 Quality Settings**

| Field                                      | Description                                             |
| ------------------------------------------ | ------------------------------------------------------- |
| **Quality Inspection Required (Purchase)** | Forces inspection before acceptance of purchased goods. |
| **Quality Inspection Required (Delivery)** | Ensures finished goods meet quality before dispatch.    |
| **Inspection Template**                    | Predefined template for quality checks.                 |

---

## **3.6 Attributes & Variants (If Item Has Variants)**

| Field                                        | Description                                                           |
| -------------------------------------------- | --------------------------------------------------------------------- |
| **Attributes (Size, Color, Material, etc.)** | Parameters used for generating item variants.                         |
| **Variant Templates**                        | Used to auto-generate multiple variants based on selected attributes. |
| **Variant Item Code Pattern**                | Naming logic for variants (e.g., ITEM-SIZE-COLOR).                    |

---

# **4. Item Lifecycle**

The item participates in multiple business processes:

1. **Created and approved** in Item Master
2. **Used in purchasing** – appears in Material Request, PO, Purchase Receipt
3. **Used in stock operations** – used in Stock Entry, Delivery Note, valuations
4. **Used in sales** – Sales Order, Quotation, Delivery Note
5. **Used in manufacturing** – BOM, Work Order, Production Plan
6. **Reports** – Stock Ledger, Item Price, Stock Balance, Analytics

---

# **5. Validations & Controls**

The system enforces important validations:

| Validation                                 | Purpose                              |
| ------------------------------------------ | ------------------------------------ |
| Cannot delete item used in transactions    | Ensures data integrity.              |
| Serial/Batch rules must match transactions | Prevents mismatched stock entries.   |
| Negative stock restriction (if enabled)    | Prevents over-issuance of inventory. |
| UOM conversion accuracy                    | Ensures correct stock valuation.     |

---

# **6. Integration with Other Modules**

| Module            | How Item Integrates                                              |
| ----------------- | ---------------------------------------------------------------- |
| **Buying**        | Appears in Material Request, Purchase Order, Supplier Quotation. |
| **Selling**       | Used in Sales Orders, Delivery Notes, Pricing.                   |
| **Manufacturing** | Used in BOM, Work Orders, routing consumption.                   |
| **Quality**       | Linked to inspection and test templates.                         |
| **Projects**      | Material requirement planning for project tasks.                 |

---

# **7. When to Create a New Item?**

Create a new item when:

* It is a unique product with different specifications.
* The unit of measure is different.
* The pricing or taxation differs.
* Item requires different stock tracking rules (batch/serial).
* Item is manufactured or purchased separately.

