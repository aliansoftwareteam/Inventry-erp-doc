# 📘 **Stock Entry – Detailed Documentation**

A **Stock Entry** is an operational document used to record **internal stock movements**, **adjustments**, or **manufacturing-related inventory actions**.
It supports multiple material movement scenarios and ensures accurate, traceable updates to stock levels across warehouses.

Stock Entry is one of the most critical documents in Inventory and Manufacturing workflows.

---

# **1. Purpose of Stock Entry**

A Stock Entry is used to:

* Transfer stock between warehouses.
* Issue materials for internal consumption.
* Receive finished goods from manufacturing.
* Consume raw materials during production.
* Repack or reconstruct items into new forms.
* Scrap damaged or unusable items.
* Return excess materials to stores.

It ensures that every internal material movement is properly documented and controlled.

---

# **2. Stock Entry Types**

Each Stock Entry type serves a specific operational purpose:

| Stock Entry Type      | Purpose                                                                      |
| --------------------- | ---------------------------------------------------------------------------- |
| **Material Transfer** | Move items from one warehouse to another.                                    |
| **Material Issue**    | Issue materials for internal use or to departments.                          |
| **Material Receipt**  | Receive items without purchase documents (internal production, adjustments). |
| **Manufacture**       | Record consumption of raw materials and receipt of finished goods.           |
| **Repack**            | Combine or split items into different units or packages.                     |
| **Subcontract**       | Send raw materials to subcontractors (if supported).                         |
| **Scrap**             | Record damaged, expired, or unusable inventory.                              |
| **Return**            | Return unused materials back to stores or warehouse.                         |

---

# **3. Workflow Overview**

Depending on the Stock Entry type, the workflow varies:

### **A. Material Transfer**

Stock Entry → Pick Items → Submit → Stock Moves to Target Warehouse

### **B. Material Issue**

Stock Entry → Consumption Logged → Stock Reduces

### **C. Manufacture**

Work Order → Stock Entry (Manufacture) →
Raw Material Consumed → Finished Goods Received

### **D. Repack**

Stock Entry → Input Materials → Output Items Created

### **E. Scrap**

Stock Entry → Stock Reduced → Scrap Report Updated

Stock Entry is a **multi-purpose tool** used for both manufacturing and non-manufacturing stock operations.

---

# **4. Key Use Cases**

* Moving materials between main and branch warehouses.
* Issuing materials to maintenance, QA, R&D, production, or admin departments.
* Manufacturing finished goods from raw materials.
* Repacking bulk items into smaller units (e.g., 50kg → 5kg bags).
* Creating kits internally.
* Returning excess materials from workstations.
* Recording scrap due to defects or wastage.

---

# **5. Stock Entry Form – Detailed Fields**

Below is a complete explanation of fields typically found in Stock Entry.

---

## **5.1 Basic Information**

| Field                   | Description                                                            |
| ----------------------- | ---------------------------------------------------------------------- |
| **Stock Entry Type**    | Defines the purpose of the entry (Transfer, Issue, Manufacture, etc.). |
| **Posting Date & Time** | When the stock movement is recorded.                                   |
| **Purpose / Remarks**   | Details about why the movement is happening.                           |
| **Company**             | Auto-selected based on setup.                                          |

---

## **5.2 Items Table (Material Details)**

Each row represents an item being moved or transformed.

| Field                | Description                               |
| -------------------- | ----------------------------------------- |
| **Item Code**        | The item involved in the movement.        |
| **Item Name**        | Auto-fetched name of the item.            |
| **Quantity**         | Quantity of item being moved or consumed. |
| **UOM**              | Unit of Measure.                          |
| **Source Warehouse** | From where items are taken.               |
| **Target Warehouse** | Where items are moved/received.           |
| **Batch No**         | Required if the item is batch-tracked.    |
| **Serial No**        | Required if the item is serial-tracked.   |
| **Description**      | Optional notes on specific items.         |

**Note:**
Source and target warehouses depend on the Stock Entry Type.

---

## **5.3 Additional Fields**

| Field                   | Description                                      |
| ----------------------- | ------------------------------------------------ |
| **Work Order**          | Used when Stock Entry is linked to production.   |
| **FG Warehouse**        | Warehouse where finished goods are received.     |
| **RM Warehouse**        | Warehouse where raw materials are consumed from. |
| **Inspection Required** | Indicates QC check requirement after entry.      |

---

# **6. Stock Behavior Based on Stock Entry Type**

### **6.1 Material Transfer**

* Stock moves from Source Warehouse → Target Warehouse.
* No material consumption occurs.

### **6.2 Material Issue**

* Stock reduces from Source Warehouse.
* Used for internal usage (e.g., maintenance, R&D, office supplies).

### **6.3 Material Receipt**

* Stock increases in Target Warehouse.
* Used when receiving goods internally not linked to purchase.

### **6.4 Manufacture**

Used in production:

* **Raw materials decrease** from RM Warehouse.
* **Finished goods increase** in FG Warehouse.
* System may auto-fetch BOM-based materials if linked with a Work Order.

### **6.5 Repack**

* Convert one or more items into different UOM or new items.
* Example: Bulk → Retail packaging.

### **6.6 Scrap**

* Removes defective/expired/damaged stock.
* Helps maintain accurate inventory.

### **6.7 Return**

* Items move back to stores/warehouse.

---

# **7. Validations & Rules**

| Rule                                                   | Purpose                            |
| ------------------------------------------------------ | ---------------------------------- |
| Source warehouse must have sufficient stock            | Prevents negative stock.           |
| Required batch/serial numbers must be selected         | Ensures accurate stock tracking.   |
| Quantity cannot be zero or negative                    | Ensures logical stock entries.     |
| For Manufacture type: FG Qty must match RM consumption | Ensures accurate production entry. |
| Cannot edit submitted entries                          | Ensures auditability.              |

---

# **8. Stock Entry Status Flow**

| Status        | Description                     |
| ------------- | ------------------------------- |
| **Draft**     | Entry is being prepared.        |
| **Submitted** | Stock is updated in the system. |
| **Cancelled** | Stock movement is reversed.     |

---

# **9. Integration with Other Modules**

| Module               | Integration Behavior                                                                 |
| -------------------- | ------------------------------------------------------------------------------------ |
| **Material Request** | Stock Entry fulfills Material Issue, Transfer, or Manufacture requests.              |
| **Work Order**       | Manufacture and Material Transfer entries are created based on production workflows. |
| **BOM**              | Auto-fetches raw material consumption for Manufacture entries.                       |
| **Quality Module**   | Optional QC checks before accepting stock.                                           |
| **Projects**         | Material issued can be tagged to a project.                                          |

---

# **10. Example Scenarios**

### 📌 **Scenario 1 – Material Transfer**

Move 50 units of RawMaterial-01 from Main Warehouse → Production Floor.

### 📌 **Scenario 2 – Manufacturing**

Consume 10kg of chemical A + 5L of chemical B
Produce 15kg of FinishedProduct-C.

### 📌 **Scenario 3 – Repack Operation**

1 Large Drum (50L) → 5 Small Cans (10L each).

### 📌 **Scenario 4 – Scrap Due to Damage**

2 cartons damaged during transit → Scrap entry created.

---

# **11. Summary**

Stock Entry plays a central role in:

* Recording all internal stock movements
* Supporting manufacturing workflows
* Managing stock accuracy
* Documenting repack, scrap, and material issues
* Ensuring proper warehouse coordination

It is one of the most versatile and operationally important documents in the inventory system.

---