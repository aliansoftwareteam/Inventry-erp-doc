# 📘 **Stock Reconciliation – Detailed Documentation**

A **Stock Reconciliation** is an operational adjustment document used to correct or realign the actual physical stock with the system-recorded stock.
It is typically used during **stock audits**, **cycle counts**, **warehouse reorganizations**, or when stock discrepancies are discovered.

Stock Reconciliation ensures that the recorded inventory aligns with the actual quantities available in the warehouse, maintaining accuracy across all inventory-dependent processes.

---

# **1. Purpose of Stock Reconciliation**

Stock Reconciliation is used to:

* Correct stock discrepancies found during physical stock counts.
* Update actual quantities for items in the system.
* Set opening stock during initial system implementation.
* Adjust stock for damaged, missing, or excess items.
* Realign stock when warehouse structures change (bins, racks, etc.).
* Support periodic cycle counts for ongoing accuracy.
* Update batch- and serial-wise quantities with accurate counts.

---

# **2. When Stock Reconciliation is Used**

Stock Reconciliation is commonly used in:

### ✔ Physical stock audits

Annual, monthly, or cycle counts.

### ✔ Go-live implementation

Setting initial stock levels when implementing a new ERP.

### ✔ Warehouse restructuring

Reallocating stock to new locations or bins.

### ✔ Discrepancy correction

Fixing mismatches between system and physical stock.

### ✔ Damage or shrinkage adjustment

If stock is lost, expired, broken, or misplaced.

### ✔ Batch/serial corrections

Realigning batch-wise or serial-wise counts.

---

# **3. How Stock Reconciliation Works**

* User enters the **actual quantity** counted in the warehouse.
* System compares this to the **current system quantity**.
* Difference is adjusted internally to match the correct quantity.
* Batch/serial numbers can be added or corrected.
* Warehouse and bin-level adjustments are supported.

**Example:**
System shows 100 units
Physical count shows 95 units
Stock Reconciliation updates system stock to **95 units**.

---

# **4. Stock Reconciliation Form – Detailed Fields**

---

## **4.1 Basic Information**

| Field                   | Description                                                                             |
| ----------------------- | --------------------------------------------------------------------------------------- |
| **Posting Date & Time** | When the adjustment is applied.                                                         |
| **Purpose / Remarks**   | Notes on why reconciliation is being done.                                              |
| **Company**             | Organization for which stock is being corrected.                                        |
| **Warehouse**           | Warehouse where reconciliation is performed (optional if multiple warehouses are used). |

---

## **4.2 Items Table (Stock Adjustment Lines)**

Each row represents one item to be reconciled.

| Field                           | Description                                   |
| ------------------------------- | --------------------------------------------- |
| **Item Code**                   | Item being counted.                           |
| **Item Name**                   | Auto-fetched for clarity.                     |
| **Current Qty (System Qty)**    | System’s recorded stock.                      |
| **Actual Qty (Physical Count)** | Quantity based on physical verification.      |
| **Difference Qty**              | Auto-calculated difference (Actual – System). |
| **UOM**                         | Unit of measure.                              |
| **Warehouse**                   | Warehouse or bin where the item is located.   |
| **Batch No**                    | Required for batch-tracked items.             |
| **Serial No**                   | Required for serialized items.                |
| **Reason**                      | Optional explanation for discrepancy.         |

---

# **5. Stock Reconciliation Behavior**

### **5.1 Updating Stock Quantities**

When submitted:

* If actual qty > system qty → system **adds** quantity.
* If actual qty < system qty → system **reduces** quantity.
* Stock balances are updated for each item and warehouse.

### **5.2 Batch-Level Adjustment**

For batch items:

* Batch-level quantities are updated.
* New batches can be created if needed.

### **5.3 Serial Number Adjustment**

For serialized items:

* Missing or extra serial numbers can be added or removed.
* Serial status is updated accordingly.

### **5.4 Multiple Warehouses**

A single reconciliation can include multiple warehouses.

### **5.5 Bin-Level Reconciliation**

For systems using bin/locator management:

* Reconciliation aligns the bin-level stock with physical reality.

---

# **6. Best Practices Before Reconciling Stock**

* Freeze warehouse operations before starting counting.
* Export and print stock reports for comparison.
* Use barcode scanners for accuracy.
* Count warehouse bin-by-bin to avoid duplication.
* Separate damaged, usable, and quarantine stock.
* Verify serial numbers and batch labels carefully.
* Have a supervisor review discrepancies before final submission.

---

# **7. Practical Use Cases**

### 📌 **Use Case 1 – Cycle Count Adjustment**

Warehouse performs weekly cycle count → 5 items mismatched → Stock Reconciliation used to correct.

---

### 📌 **Use Case 2 – Annual Audit**

Entire warehouse audited → results entered via Stock Reconciliation → system aligns all inventory.

---

### 📌 **Use Case 3 – Stock Loss or Damage**

Damaged goods found → actual qty lower → reconciliation reduces stock.

---

### 📌 **Use Case 4 – Wrong Storage Location**

Stock found in a different bin than recorded → reconciliation fixes bin-level quantities.

---

### 📌 **Use Case 5 – Batch Correction**

Expired or missing batches corrected through batch-level reconciliation.

---

# **8. Validations & Rules**

| Rule                                                     | Purpose                            |
| -------------------------------------------------------- | ---------------------------------- |
| Can reconcile only existing items                        | Prevents invalid adjustments.      |
| Serialized items require serial numbers                  | Ensures traceability.              |
| Batch items require valid batch selection                | Maintains batch integrity.         |
| Qty cannot be negative                                   | Ensures logical stock values.      |
| Cannot edit after submission                             | Guarantees audit traceability.     |
| System locks warehouse during adjustment (if configured) | Prevents conflicting transactions. |

---

# **9. Integration with Other Modules**

| Module                         | Integration Behavior                             |
| ------------------------------ | ------------------------------------------------ |
| **Stock Ledger**               | Shows adjustment entries for traceability.       |
| **Delivery Note**              | Uses updated stock after reconciliation.         |
| **Material Request**           | Planning uses corrected stock levels.            |
| **Manufacturing (Work Order)** | Availability check uses updated quantities.      |
| **Batch & Serial Tracking**    | Reconciliation updates batch and serial records. |

---

# **10. Example Scenarios**

### 📌 **Scenario 1 – Correcting Stock Count**

System stock: 250 units
Physical stock: 260 units
Reconciliation increases stock to 260.

---

### 📌 **Scenario 2 – Adjusting Damaged Goods**

System stock: 100
Physical stock: 95
Reconciliation reduces stock by 5 damaged items.

---

### 📌 **Scenario 3 – Batch Expiry Correction**

Expired batch physically removed → reconciliation reduces batch qty to 0.

---

### 📌 **Scenario 4 – Serial Number Audit**

2 serial numbers missing → reconciliation removes them.

---

# **11. Summary**

Stock Reconciliation is essential for:

* Accurate inventory control
* Warehouse auditing
* Cycle count adjustments
* Batch and serial corrections
* Smooth manufacturing and sales operations
* Reliable inventory planning

It ensures the system reflects the true physical stock at all times.

---
