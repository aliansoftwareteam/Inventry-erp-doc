# 📘 **Pick List – Detailed Documentation**

A **Pick List** is a warehouse operation document used to guide warehouse staff in **locating, picking, and preparing items** for delivery or production.
It ensures that the correct items, quantities, and batch/serial numbers are selected from the correct warehouse locations.

Pick Lists improve order fulfillment accuracy, reduce picking errors, and streamline internal and outbound logistics.

---

# **1. Purpose of Pick List**

A Pick List is used to:

* Identify items required for a Delivery Note or Work Order.
* Guide warehouse staff to pick items from correct warehouse locations.
* Manage picking for sales, transfers, and manufacturing.
* Reduce picking errors and improve operational efficiency.
* Support batch/serial number handling.
* Optimize warehouse workflows with structured picking routes.

---

# **2. When Pick List is Used**

Pick List is typically generated:

* After Sales Order confirmation (for customer dispatch).
* Before preparing a Delivery Note.
* Before production starts (material picking for Work Orders).
* For internal stock transfers.
* For bulk dispatch or multi-item shipments.
* When strict control over warehouse operations is required.

---

# **3. Pick List Workflow Overview**

### **For Sales Delivery**

Sales Order → Pick List → Packing Slip (optional) → Delivery Note → Dispatch

### **For Production**

Work Order → Pick List → Material Transfer/Issue → Production Execution

### **For Internal Transfers**

Material Request → Pick List → Stock Entry → Delivery

Pick List acts as the bridge between planning and physical material movement.

---

# **4. Key Features of Pick List**

* Auto-fetches items from Sales Order or Work Order.
* Identifies **warehouse, bin, batch, and serial numbers**.
* Supports **partial picking**.
* Displays **exact warehouse locations** to improve picking efficiency.
* Helps warehouse staff avoid stock mismatches.
* Allows tracking of picked quantities vs required quantities.
* Supports barcode scanning for fast and accurate picking.

---

# **5. Pick List Form – Detailed Fields**

---

## **5.1 Basic Information**

| Field                     | Description                                           |
| ------------------------- | ----------------------------------------------------- |
| **Pick List Type**        | Sales, Work Order, or Internal Transfer.              |
| **Reference Document**    | Sales Order / Work Order linked to the pick list.     |
| **Customer / Department** | Delivery recipient or department needing materials.   |
| **Warehouse**             | The source warehouse from which items are picked.     |
| **Company**               | Organization for which picking is done.               |
| **Pick List Date**        | Date when the pick list is generated.                 |
| **Remarks**               | Additional instructions or notes for warehouse staff. |

---

## **5.2 Items Table (Pick Items)**

Each row shows an item that must be picked.

| Field                     | Description                                   |
| ------------------------- | --------------------------------------------- |
| **Item Code**             | Item to be picked.                            |
| **Required Qty**          | Quantity required for delivery/production.    |
| **Picked Qty**            | Quantity actually picked by warehouse staff.  |
| **UOM**                   | Unit of measure.                              |
| **Warehouse Location**    | Specific location/bin where item is stored.   |
| **Batch No**              | If item is batch-controlled.                  |
| **Serial No**             | If item requires serial tracking.             |
| **Stock Qty in Location** | Available quantity at the specified location. |
| **Description**           | Extra details for clarity.                    |

Pickers use this table to locate and collect the items quickly.

---

# **6. Location & Storage Mapping**

One of the strongest features of a Pick List is **item location mapping**, including:

* Warehouse
* Bin / Rack / Shelf
* Batch
* Serial numbers

This enables:

✔ Faster picking
✔ Fewer mistakes
✔ Better inventory accuracy
✔ Efficient warehouse navigation

---

# **7. Pick List Operations**

### **7.1 Auto-Fetching Items**

Based on the linked Sales Order or Work Order, items automatically populate with:

* Required quantities
* Reduced quantities (if partial picking already done)
* Available warehouse locations

### **7.2 Partial Picking**

If full quantity cannot be picked:

* Picker enters the amount available.
* Remaining qty stays pending for future picking.

### **7.3 Batch / Serial Handling**

For batch or serial items:

* System displays all available batches.
* Picker selects batch/serial numbers.
* Ensures traceability and compliance.

### **7.4 Multi-warehouse Picking**

If items are stored across multiple warehouses:

* Pick List shows the best warehouse or bin to pick from.
* Can consolidate items from multiple locations.

---

# **8. Pick List Status Flow**

| Status                  | Description                                   |
| ----------------------- | --------------------------------------------- |
| **Draft**               | Pick List created but not completed.          |
| **In Progress**         | Picking started; some items picked.           |
| **Completed**           | All required items picked.                    |
| **Partially Completed** | Some items picked; some pending.              |
| **Cancelled**           | Pick List voided; no further picking allowed. |

---

# **9. Validations & Rules**

| Rule                                       | Purpose                           |
| ------------------------------------------ | --------------------------------- |
| Picked Qty cannot exceed Required Qty      | Prevents over-picking.            |
| Batch/Serial required for relevant items   | Ensures accurate picking.         |
| Warehouse must match the selected location | Prevents stock mismatches.        |
| Only available quantity can be picked      | Ensures real-time stock accuracy. |
| Cannot modify once completed               | Maintains traceability.           |

---

# **10. Integration with Other Modules**

*(Accounting-free as requested)*

| Module            | Integration Behavior                                        |
| ----------------- | ----------------------------------------------------------- |
| **Sales Order**   | Auto-fetch items for customer delivery.                     |
| **Delivery Note** | Uses picked items for dispatch.                             |
| **Work Order**    | Picks raw materials for manufacturing.                      |
| **Stock Entry**   | Moves picked materials to production floor or packing area. |
| **Packing Slip**  | Provides packing reference after items are picked.          |
| **Delivery Trip** | Helps logistics team plan vehicle loading.                  |

---

# **11. Example Scenarios**

### 📌 **Scenario 1 – Customer Delivery**

Sales Order = 20 units
Pick List → warehouse staff picks items → Delivery Note → Dispatch

---

### 📌 **Scenario 2 – Manufacturing Material Picking**

Work Order needs raw materials:
Steel Rod, 10 pcs
Flange, 4 pcs

Pick List generated → items picked → Stock Entry issued to production.

---

### 📌 **Scenario 3 – Multi-Bin Picking**

Item is spread across 3 bins:

* Bin A: 5 pcs
* Bin B: 10 pcs
* Bin C: 15 pcs

Pick List shows all bins → picker picks 20 pcs from best combination.

---

### 📌 **Scenario 4 – Partial Stock Availability**

Required: 50 pcs
Available: 30 pcs
Picked: 30 pcs
Remaining: 20 pcs (pending for next picking cycle)

---

# **12. Summary**

The Pick List is essential for:

* Accurate warehouse picking
* Smooth dispatch and delivery
* Efficient manufacturing material handling
* Error-free stock movement
* Controlled operational workflow

It ensures the right materials are picked from the right place at the right time.

---
