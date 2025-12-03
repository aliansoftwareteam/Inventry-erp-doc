# 📘 **Bill of Materials (BOM) – Detailed Documentation**

---

# **1. Introduction**

A **Bill of Materials (BOM)** defines the complete structure of a product, including:

* Materials
* Sub-assemblies
* Multi-level nested BOMs
* Quantities and scrap
* Routing operations
* Costing components

A BOM acts as the **manufacturing recipe**, allowing you to build simple and highly complex products with multiple assembly levels.

---

# **2. Purpose of BOM**

A BOM is used to:

* Represent a product structure in single-level or multi-level format
* Plan raw material and sub-assembly requirements
* Calculate manufacturing costs
* Define routing and operational steps
* Generate work orders (parent or child work orders)
* Maintain version-controlled assemblies

---

# **3. Multi-Level BOM (Core Feature)**

This is the **key update you requested**.

A **Multi-Level BOM** means:

* A BOM can include **other BOMs as components**
* Sub-assemblies can have their **own independent BOMs**
* The system recursively expands all levels for material planning

### Example:

```
Finished Product (BOM 1)
│
├── Sub Assembly A (BOM 2)
│   ├── Component 1
│   └── Component 2
│
├── Sub Assembly B (BOM 3)
│   └── Component 3
│
└── Component 4
```

### System Capabilities:

✔ You can **select another BOM** inside a BOM
✔ Multi-level expansion for planning and costing
✔ Multi-level stock availability checks
✔ Auto-generation of child Work Orders (if needed)
✔ Accurate multi-level cost roll-up

---

# **4. BOM Structure**

The BOM contains the following major parts:

---

## **4.1 Basic Details**

| Field                | Description                                          |
| -------------------- | ---------------------------------------------------- |
| **BOM ID**           | Unique BOM number for this assembly.                 |
| **Item**             | Product or sub-assembly manufactured using this BOM. |
| **Quantity**         | Default quantity for the BOM (e.g., 1 unit).         |
| **BOM Type**         | Production / Engineering / Subcontracting.           |
| **BOM Is Active**    | Whether this BOM is currently used.                  |
| **Default BOM**      | The primary BOM for this item.                       |
| **Version/Revision** | Used for design changes and control.                 |

---

## **4.2 Component Details (Materials + Sub Assemblies)**

### **Components Section Includes:**

| Field                | Description                                                       |
| -------------------- | ----------------------------------------------------------------- |
| **Item / Component** | Raw material OR another item with its own BOM.                    |
| **Has BOM**          | Indicates if the selected item has its own BOM (sub-assembly).    |
| **Linked BOM**       | The sub-assembly BOM selected for this item (BOM 2, BOM 3, etc.). |
| **Required Qty**     | Quantity needed for finished qty.                                 |
| **Scrap %**          | Expected wastage.                                                 |
| **UOM**              | Units of measurement.                                             |
| **Warehouse**        | Default source location.                                          |

### ✔ This fulfills your requirement:

> “BOM should be multi-level like I can select another BOM in 2nd BOM.”

Yes — in this section, whenever you select an item that has its own BOM, the system allows you to:

* Attach the **sub-assembly BOM**
* Decide whether that sub-assembly should be **produced or purchased**
* Expand it during planning

---

## **4.3 Operations / Routing**

Operations define the manufacturing sequence.

| Field              | Description                            |
| ------------------ | -------------------------------------- |
| **Operation Name** | Example: Cutting, Machining, Assembly. |
| **Workstation**    | Machine area where operation runs.     |
| **Setup Time**     | Time needed for preparation.           |
| **Operation Time** | Time needed to produce batch or unit.  |
| **Cycle Time**     | Time per unit.                         |
| **Batch Size**     | How many units done per cycle.         |
| **Labor Cost**     | Labor rate for the operation.          |
| **Machine Cost**   | Machine time cost allocation.          |

For multi-level BOMs:

* Sub-assembly operations are part of their own BOM
* Parent operations appear only at the top level

---

# **5. Costing in Multi-Level BOM**

System rolls up costs from all levels:

### Includes:

* Cost of raw materials
* Cost of sub-assemblies
* Labor and machine cost
* Overheads

### Multi-Level Cost Roll-Up:

```
Sub Assembly BOM Cost (BOM 2)
     ↓
Component of Parent BOM
     ↓
Final BOM Cost
```

✔ Each nested BOM calculates its cost separately
✔ Parent BOM automatically adds sub-assembly cost

---

# **6. BOM Lifecycle (Multi-Level)**

```
1. Create Parent Item
2. Create Sub-Assembly Items (optional)
3. Create BOMs for each sub-assembly
4. Create Parent BOM and add sub-assembly items with BOM links
5. Validate all levels
6. Use BOM for Work Orders or Production Plan
7. Child Work Orders auto-create (optional)
8. Update versions as changes occur
```

---

# **7. Multi-Level BOM in Production Flow**

| Stage                         | System Behavior                                                   |
| ----------------------------- | ----------------------------------------------------------------- |
| **Production Planning (MRP)** | Expands all sub-assembly levels.                                  |
| **Work Order Creation**       | Creates WO for parent; optionally separate WO for sub-assemblies. |
| **Material Issue**            | Breaks down all levels into required raw materials.               |
| **Costing**                   | Rolls up cost of sub-assemblies.                                  |
| **Quality**                   | QC can happen at each sub-assembly level.                         |

---

# **8. Sub-Assembly Handling Options**

System supports three approaches for sub-assemblies:

### ✔ **1. Auto Manufacture (Child Work Orders)**

The system generates separate WOs for sub-assemblies.

### ✔ **2. Backflush at Parent Level**

No child WOs — sub-assemblies explode into raw materials.

### ✔ **3. Purchase Sub-Assembly as a Complete Item**

Treat the sub-assembly as a buy item instead of manufacturing.

---

# **9. BOM Reports (Multi-Level Enabled)**

| Report                            | Purpose                                                      |
| --------------------------------- | ------------------------------------------------------------ |
| **BOM Search**                    | Search BOMs by item or version.                              |
| **BOM Stock Report**              | Shows stock availability for each level of BOM.              |
| **BOM Operations Time**           | Total operation time across all nested levels.               |
| **Work Order Consumed Materials** | Tracks actual usage of materials from parent + child levels. |
| **Production Planning Report**    | Shows expanded raw material requirement for all BOM levels.  |

---

# **10. Benefits of Multi-Level BOM**

* Supports complex product engineering
* Accurate raw material planning
* Automated cost roll-up
* Child work order generation
* Clear visibility of sub-assemblies
* Easier control on design changes
* Reduces production errors
* Helps modular manufacturing

---

# **11. When to Use Multi-Level BOM**

Use multi-level BOM when:

* Items have sub-assemblies
* Product is built in stages
* Multiple departments work on different assemblies
* You want accurate costing
* You need independent QC for each assembly
* Product is custom-engineered or configurable

---