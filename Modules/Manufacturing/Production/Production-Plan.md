# 📘 **Production Plan – Detailed Documentation**

---

# **1. Introduction**

A **Production Plan** is a structured manufacturing schedule that determines:

* What to produce
* How much to produce
* When to produce
* Which materials are required
* Which resources (workstations, labor, shifts) will be used

It aligns **demand, inventory, work orders, and capacity** to ensure production happens smoothly and on time.

Production Plan is often created based on:

* Sales Orders
* Forecasting
* Material Requirements Planning (MRP)
* Reorder Levels
* Internal Production Requests

It serves as the foundation for generating Work Orders and driving the production process.

---

# **2. Purpose of Production Plan**

Production Planning helps manufacturers:

* Plan production quantities for a given period
* Ensure material availability before production starts
* Avoid stock-outs or excess inventory
* Optimize machine and labor capacity
* Balance workload across workstations
* Align manufacturing with customer delivery dates
* Trigger Work Orders based on actual needs

It acts as the bridge between **demand planning** and **shop floor execution**.

---

# **3. When Production Plan Is Created**

A Production Plan is created when:

### ✔ Demand exists (Sales Orders or Forecast)

Plan production based on customer orders or expected demand.

### ✔ Stock is insufficient

System identifies shortage based on BOM and inventory.

### ✔ MRP suggests production

Automated planning recommends work orders.

### ✔ Seasonal or batch production is needed

For industries like garments, food, and engineering.

### ✔ Planning period begins

Weekly, monthly, or custom planning cycles.

---

# **4. Components of a Production Plan**

A Production Plan consists of several sections that define what will be produced and how.

---

## **4.1 Basic Details**

| Field                  | Description                                     |
| ---------------------- | ----------------------------------------------- |
| **Production Plan ID** | Unique identifier for the plan.                 |
| **Planned Start Date** | When production should begin.                   |
| **Planned End Date**   | Target completion date.                         |
| **Company**            | Company for which the plan is prepared.         |
| **Purpose**            | Make-to-Order / Make-to-Stock / Forecast-Based. |

---

## **4.2 Item Requirement Section**

This section defines the **final items** planned for production.

| Field                      | Description                                |
| -------------------------- | ------------------------------------------ |
| **Item**                   | Final product to be manufactured.          |
| **Required Quantity**      | Total quantity needed for planning period. |
| **Available Quantity**     | Current stock of finished goods.           |
| **Shortage Quantity**      | Required – Available.                      |
| **Planned Production Qty** | Quantity to be manufactured.               |
| **Warehouse**              | Warehouse for finished goods.              |

Production plan decides which items require Work Orders.

---

## **4.3 BOM & Routing Details**

When items have BOMs:

* System fetches materials & operations
* Routing determines cycle time
* Multi-level BOM is expanded to calculate requirements

This section ensures:

* Accurate material requirement calculation
* Correct operational planning

---

## **4.4 Material Requirements Section (MRP Integration)**

This section lists **all raw materials and sub-assemblies** required.

| Field                  | Description                            |
| ---------------------- | -------------------------------------- |
| **Material Item**      | Raw material/component.                |
| **Total Required Qty** | Required for entire plan based on BOM. |
| **Available Stock**    | Stock currently available.             |
| **Shortage Qty**       | How much stock is missing.             |
| **Action**             | Purchase, Transfer, or Manufacture.    |
| **Warehouse**          | From where material will be issued.    |

This is essential for procurement and inventory teams.

---

## **4.5 Work Order Creation Section**

From the Production Plan, you can create:

### ✔ **Work Orders for Final Items**

If parent items need to be manufactured.

### ✔ **Work Orders for Sub-Assemblies**

If BOM contains multi-level assembly requirements.

Options include:

* Auto-create Work Orders
* Manually review quantities before creating
* Create Work Orders only for shortage quantities

---

## **4.6 Capacity Planning Section**

Capacity planning helps ensure resources can handle the planned workload.

| Field                    | Description                                 |
| ------------------------ | ------------------------------------------- |
| **Workstation Load**     | Total hours required per workstation.       |
| **Shift Availability**   | Hours available per shift.                  |
| **Total Capacity Hours** | Machine time available for planning period. |
| **Overload/Underload**   | Highlights imbalance in scheduling.         |

This ensures no machine is overloaded beyond capacity.

---

## **4.7 Production Timeline / Scheduling**

Some production plans include Gantt-style scheduling:

* Visual timeline of operations
* Lead time per item
* Expected delays
* Task dependencies
* Production commitments

This improves visibility and delivery reliability.

---

# **5. Production Plan Workflow**

```
Plan Created  
    ↓  
Select Items to Produce  
    ↓  
System Expands BOM (Multi-Level)  
    ↓  
Calculate Material Requirements  
    ↓  
Check Stock Availability  
    ↓  
Highlight Shortages  
    ↓  
Suggest Purchase/Production Requirements  
    ↓  
Generate Work Orders  
    ↓  
Monitor Production Against Plan
```

---

# **6. Types of Production Plans**

| Type                      | Usage                                        |
| ------------------------- | -------------------------------------------- |
| **Make-to-Stock Plan**    | Produce based on forecast or regular demand. |
| **Make-to-Order Plan**    | Produce based only on customer orders.       |
| **Hybrid Plan**           | Mix of forecast + sales orders.              |
| **Batch / Seasonal Plan** | Used in food, apparel, electronics, etc.     |
| **MRP-Driven Plan**       | Fully automated based on BOM + stock levels. |

---

# **7. Benefits of a Production Plan**

* Ensures smooth material flow
* Prevents production delays
* Reduces stock-out risk
* Minimizes excess inventory
* Optimizes use of machines and labor
* Improves customer delivery performance
* Reduces urgent purchases
* Enables accurate cost estimation
* Improves inter-department coordination

---

# **8. Production Plan Reports**

| Report                             | Purpose                                                      |
| ---------------------------------- | ------------------------------------------------------------ |
| **Production Planning Report**     | Shows required quantities, shortages, and item readiness.    |
| **Material Requirement Report**    | Multi-level BOM expansion with required material quantities. |
| **Work Order Summary**             | Status of Work Orders created from the plan.                 |
| **Capacity Load Report**           | Identifies overloaded workstations.                          |
| **Production Analytics Dashboard** | Uses plan data to track progress vs target.                  |

---

# **9. Integration Points**

Production Plan integrates with:

| Module                   | Role                                          |
| ------------------------ | --------------------------------------------- |
| **BOM**                  | Determines materials and operations required. |
| **Routing**              | Helps calculate total production time.        |
| **Work Order**           | Generated directly from the plan.             |
| **Inventory**            | Checks stock and calculates shortages.        |
| **Procurement**          | Raises purchase requests for shortages.       |
| **Production Analytics** | Tracks planned vs actual performance.         |

---

# **10. When to Use a Production Plan**

Create a Production Plan when:

* You need consolidated manufacturing planning
* You work with multi-level BOMs
* You want to generate multiple Work Orders at once
* You want proper material & capacity planning
* You must meet customer delivery dates
* You want to plan weekly or monthly production cycles
* You need traceability between demand and manufacturing
