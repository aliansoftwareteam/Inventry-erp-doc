
# 📘 **Batch – Detailed Documentation**

A **Batch** represents a group of items produced or received together under similar manufacturing or procurement conditions.
Batch tracking is used when items share attributes such as **manufacture date, expiry date, lot number, or production cycle**.

Batch management provides traceability, quality control, and regulatory compliance for industries like **pharmaceuticals, chemicals, food & beverages, cosmetics, manufacturing**, and any business where goods must be tracked by lot.

---

# **1. Purpose of Batch Tracking**

Batch tracking is used to:

* Group identical items produced or received at the same time.
* Track expiry dates and shelf life.
* Identify defective or recalled lots.
* Improve traceability for quality audits.
* Simplify stock handling for bulk-produced items.
* Support manufacturing and procurement processes.

Batch tracking ensures safe, compliant, and traceable inventory management.

---

# **2. When Batches Are Used**

Batch tracking is essential for:

### ✔ Perishable goods

(Food, beverages, dairy, meat)

### ✔ Pharmaceuticals

(Medicine, vaccines, injectables)

### ✔ Chemicals

(Adhesives, paint, solvents)

### ✔ Cosmetics

(Lotions, creams, perfumes)

### ✔ Manufacturing

(Bulk production batches)

### ✔ Items with expiry or best-before dates

---

# **3. How Batch Management Works**

A batch is created when:

### **A. Items are received from a supplier**

During Purchase Receipt → new batch is assigned or scanned.

### **B. Items are manufactured internally**

During Stock Entry (Manufacture) → system creates a batch for finished goods.

### **C. Items are repacked or relabelled**

Repack Stock Entry can generate new batch numbers.

### **D. Items are split across warehouses**

Same batch can exist in multiple warehouses.

Batch numbers ensure traceability across transitions.

---

# **4. Batch Structure**

Each Batch record stores:

* Batch Number
* Item Code
* Manufacture Date
* Expiry Date
* Batch Quantity
* Warehouse locations
* Incoming transaction reference

---

# **5. Batch Form – Detailed Fields**

---

## **5.1 Basic Information**

| Field                   | Description                               |
| ----------------------- | ----------------------------------------- |
| **Batch No**            | Unique identifier for the batch.          |
| **Item Code**           | Item that this batch belongs to.          |
| **Item Name**           | Auto-fetched item description.            |
| **Batch Creation Date** | When the batch was created in the system. |

---

## **5.2 Batch Attributes**

| Field                         | Description                                      |
| ----------------------------- | ------------------------------------------------ |
| **Manufacture Date**          | Production date of the batch.                    |
| **Expiry Date / Best Before** | When the batch should no longer be used or sold. |
| **Batch Description**         | Additional notes or specifications.              |

These fields ensure regulatory and operational compliance.

---

## **5.3 Incoming Source Details**

| Field                         | Description                             |
| ----------------------------- | --------------------------------------- |
| **Purchase Receipt**          | If batch created from supplier receipt. |
| **Stock Entry (Manufacture)** | If batch produced internally.           |
| **Repack Entry**              | For repacked or relabelled items.       |
| **Supplier / Manufacturer**   | Source of the batch.                    |

---

## **5.4 Location & Quantity Tracking**

| Field                  | Description                                 |
| ---------------------- | ------------------------------------------- |
| **Warehouse / Bin**    | Where the batch is physically stored.       |
| **Available Quantity** | Current stock for this batch.               |
| **Reserved Quantity**  | Quantity reserved for orders or production. |
| **Delivered Quantity** | Quantity already dispatched.                |

Batch quantity updates automatically based on stock movements.

---

## **5.5 Quality & Compliance Fields**

| Field                           | Description                                       |
| ------------------------------- | ------------------------------------------------- |
| **Quality Inspection Required** | Indicates if QC must be performed before release. |
| **Inspection Result**           | Accepted / Rejected quantities.                   |
| **Holding Warehouse**           | Temporary storage for items awaiting QC.          |

---

# **6. Batch Behavior in Operations**

### **6.1 Purchase Receipt**

* New batch auto-generated or selected.
* Batch expiry/manufacture dates are recorded.

### **6.2 Stock Entry (Manufacture)**

* Batch created for finished goods.
* Used for production traceability.

### **6.3 Delivery / Sales**

* System requires selecting a batch number for batch-tracked items.
* Ensures correct FIFO, FEFO, expiry control.

### **6.4 Internal Transfers**

* Same batch can be moved across warehouses without altering its identity.

### **6.5 Returns**

* Returned goods remain tied to the original batch number.

---

# **7. Batch Features & Advantages**

### ✔ **Full Traceability**

Track the path of a batch from creation → storage → delivery → return.

### ✔ **Expiry Management**

Supports FEFO (First Expiry, First Out) handling.

### ✔ **Safety & Compliance**

Important for regulated industries.

### ✔ **Quality Control**

Batch-level testing and inspection support.

### ✔ **Efficient Recall Management**

Quickly identify and isolate defective batches.

### ✔ **Warehouse Optimization**

Exact quantities per batch per location are visible.

---

# **8. Batch Lifecycle**

A typical batch lifecycle:

```
Create Batch → Store in Warehouse → Pick & Deliver → Track Expiry → Return / Scrap (if needed)
```

### **1. Creation**

Purchase Receipt or Manufacturing Entry creates the batch.

### **2. Storage**

Batch is stored across one or multiple warehouses.

### **3. Picking**

Batch is selected during picking and delivery operations.

### **4. Delivery**

Batch quantity reduces as items are delivered.

### **5. Expiry Monitoring**

Batch expiry report tracks upcoming expiry dates.

### **6. Return / Scrap**

Expired or defective batches are transferred to scrap or return warehouses.

---

# **9. Validations & Rules**

| Rule                                             | Purpose                                 |
| ------------------------------------------------ | --------------------------------------- |
| Batch must belong to a single item               | Ensures correct product identification. |
| Expiry date cannot be before manufacture date    | Valid compliance.                       |
| Batch required for batch-tracked items           | Prevents missing traceability.          |
| Batch cannot be deleted if stock exists          | Integrity of stock records.             |
| Returned items must use original batch           | Ensures lifecycle tracking.             |
| QC required before batch moves to main warehouse | Ensures quality assurance.              |

---

# **10. Integration with Other Modules**

*(No accounting references included)*

| Module                               | Integration Behavior                   |
| ------------------------------------ | -------------------------------------- |
| **Purchase Receipt**                 | Creates batch for received goods.      |
| **Stock Entry (Manufacture)**        | Creates batch for produced items.      |
| **Delivery Note**                    | Requires batch selection for delivery. |
| **Pick List**                        | Suggests batches based on FEFO rules.  |
| **Quality Inspection**               | Batch-level inspection results stored. |
| **Material Request / Manufacturing** | Uses batch quantities for planning.    |

---

# **11. Example Scenarios**

### 📌 **Scenario 1 – Batch from Supplier**

* Purchase Receipt for 200 bottles of chemical X
* Batch created: **CHEMX-25022024**
* Expiry recorded: 24 months

---

### 📌 **Scenario 2 – Manufacturing Batch**

* Production of 500 tablets
* Batch created: **TAB500-LOT-05**
* Used across 3 warehouses

---

### 📌 **Scenario 3 – Expiry Management**

* Batch expiry report alerts items expiring within 30 days
* Warehouse moves them to priority dispatch

---

### 📌 **Scenario 4 – Batch Return**

Customer returns items → assigned back to original batch → quantity updated.

---

# **12. Summary**

Batch tracking provides:

* End-to-end traceability of item groups
* Control over expiry and shelf-life
* Structured quality management
* Better warehouse operations
* Simplified recall and regulatory compliance

It is essential for industries requiring accuracy, safety, and strict tracking of products.

---
