# 📘 **Warehouse – Detailed Documentation**

A **Warehouse** represents a **physical or logical storage location** where inventory is stored, managed, and tracked.
Warehouses enable multi-location inventory management, proper stock control, and efficient operational workflows across procurement, sales, manufacturing, and logistics.

Warehouse configuration forms the foundation of the entire Inventory module.

---

# **1. Purpose of Warehouse Management**

Warehouses are used to:

* Organize inventory across multiple physical locations.
* Track stock movement and quantity for each location.
* Support dispatch planning, receiving, put-away, and picking.
* Enable hierarchical warehouse structures (Main → Sub Warehouse → Bins).
* Manage dedicated storage for finished goods, raw materials, scrap, returns, etc.
* Maintain traceability of stock at a location level.
* Control access and permissions for sensitive or restricted storage zones.

Efficient warehouse management improves stock accuracy, reduces movement errors, and enhances operational performance.

---

# **2. Types of Warehouses**

Different warehouse types can be created depending on the business structure:

### ✔ **Main Warehouse**

Central storage location for high-volume or company-wide stock.

### ✔ **Raw Material Warehouse**

Used for storing materials required for manufacturing.

### ✔ **Finished Goods Warehouse**

Stores final products ready for dispatch.

### ✔ **WIP (Work-in-Progress) Warehouse**

Tracks partially manufactured goods at various production stages.

### ✔ **Quality Inspection / Quarantine Warehouse**

Temporarily holds items pending QC approval.

### ✔ **Scrap Warehouse**

Stores defective, expired, or unusable items.

### ✔ **Returns Warehouse**

For customer returns or supplier returns.

### ✔ **Regional / Branch Warehouses**

Used by remote offices, stores, or distribution centers.

### ✔ **Project Warehouses**

Assigned to specific projects or job sites.

Warehouses may be **physical locations** or **logical virtual locations** depending on the business process.

---

# **3. Warehouse Hierarchy Structure**

Warehouses can be organized in a parent-child hierarchy for better control and reporting.

Example:

```
Company Warehouse
   ├── Main Warehouse
   │     ├── RM Store
   │     ├── FG Store
   │     └── QA Hold
   ├── Branch Warehouse 1
   └── Branch Warehouse 2
```

Hierarchy helps:

* Segment stock clearly
* Set user permissions
* Generate warehouse-wise stock reports
* Support bin-level distribution

---

# **4. Warehouse Master – Detailed Fields**

---

## **4.1 Basic Details**

| Field                  | Description                                                  |
| ---------------------- | ------------------------------------------------------------ |
| **Warehouse Name**     | Unique name to identify the warehouse.                       |
| **Parent Warehouse**   | Defines hierarchical structure.                              |
| **Warehouse Type**     | Raw, Finished Goods, Scrap, Return, QC, etc.                 |
| **Is Group Warehouse** | Marks the warehouse as a parent node only (no stock stored). |

---

## **4.2 Operational Details**

| Field                     | Description                                                               |
| ------------------------- | ------------------------------------------------------------------------- |
| **Address**               | Physical location of the warehouse (optional).                            |
| **Contact Person**        | Warehouse in-charge or responsible supervisor.                            |
| **Default Warehouse For** | Set default warehouse for material receipts, deliveries, production, etc. |
| **Allow Transfers**       | Whether stock can be moved in/out of this warehouse.                      |

---

## **4.3 Storage Configuration (If Bin Management Enabled)**

| Field                        | Description                                                  |
| ---------------------------- | ------------------------------------------------------------ |
| **Storage Bins / Locations** | Sub-locations inside a warehouse (Rack A / Shelf 1 / Bin 3). |
| **Bin Capacity**             | Max storage capacity per bin.                                |
| **Picking Strategy**         | FIFO, FEFO, LIFO (operational).              |

---

## **4.4 Restrictions & Rules**

| Field                                    | Description                                            |
| ---------------------------------------- | ------------------------------------------------------ |
| **Restricted Access**                    | Controls user permissions.                             |
| **Allow Negative Stock**                 | Controlled at system settings; affects this warehouse. |
| **Prevent Dispatch from This Warehouse** | For QA Hold, Scrap, or Reserved locations.             |

---

# **5. Warehouse Operations**

Warehouses are involved in every stock movement:

### **5.1 Goods Receipt**

* Goods received from suppliers → stored in designated warehouse.

### **5.2 Internal Transfers**

* Stock moved from one warehouse to another using Stock Entry.

### **5.3 Production Movements**

* Raw materials issued to production (RM Warehouse → WIP Warehouse).
* Finished goods received into FG Warehouse.

### **5.4 Quality Control**

* Items move to QC Warehouse before approval.

### **5.5 Dispatch**

* Items picked and dispatched from Delivery Warehouse.

### **5.6 Returns & Scrap**

* Damaged/returned items stored separately.

Warehouses ensure operations are traceable and structured.

---

# **6. Warehouse Permissions**

User-level access improves security and control:

* Restrict users to specific warehouses.
* Allow role-based access (Storekeeper, QC, Production Planner).
* Prevent unauthorized stock transfers or delivery operations.

This ensures inventory integrity in larger organizations.

---

# **7. Integration with Other Modules**

| Module               | Integration Behavior                                          |
| -------------------- | ------------------------------------------------------------- |
| **Item Master**      | Items must have designated default warehouses.                |
| **Purchase Receipt** | Goods received into a selected warehouse.                     |
| **Stock Entry**      | Handles internal transfers, issues, receipts.                 |
| **Delivery Note**    | Items dispatched from warehouse reduce its stock.             |
| **Work Orders**      | Pull RM from selected warehouse; push FG into FG warehouse.   |
| **Pick List**        | Identifies warehouse and bin locations for picking.           |
| **Batch / Serial**   | Stock is tracked batch-wise or serial-wise inside warehouses. |

---

# **8. Example Scenarios**

### 📌 **Scenario 1 – Multi-Warehouse Company**

A company has:

* Central Warehouse
* Three Branch Warehouses
* Dedicated Scrap Warehouse

Stock is distributed and managed across all.

---

### 📌 **Scenario 2 – Production Workflow**

RM Warehouse → (issue) → WIP Warehouse → (output) → FG Warehouse
Warehouses track each movement accurately.

---

### 📌 **Scenario 3 – QC Workflow**

Goods received → QC Warehouse
After approval → Main Warehouse
If rejected → Rejection Warehouse

---

### 📌 **Scenario 4 – Picking & Dispatch**

Pick List identifies item location:

* Warehouse: FG Store
* Bin: RACK-B / SHELF-2 / BIN-7
  Warehouse staff picks correctly and fast.

---

# **9. Summary**

A Warehouse plays a central role in:

* Organizing and structuring inventory
* Tracking every stock movement
* Managing multi-location operations
* Improving picking, packing, and dispatch
* Supporting production, QC, and return workflows
* Ensuring accurate and real-time inventory visibility

It is one of the foundational components of the inventory management system.

---
