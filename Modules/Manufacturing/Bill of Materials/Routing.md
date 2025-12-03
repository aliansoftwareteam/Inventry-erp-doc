
# 📘 **Routing – Detailed Documentation**

---

# **1. Introduction**

**Routing** defines the *sequence of operations* required to manufacture a product.
It acts as the **manufacturing workflow blueprint**, specifying:

* What operations to perform
* In what order
* At which workstation
* How long each operation takes
* Cost of each operation
* Dependencies between operations

Routing is essential for Work Orders, Job Cards, production planning, costing, and shop-floor execution.

---

# **2. Purpose of Routing**

Routing helps manufacturers:

* Standardize the production process
* Ensure correct sequence of operations
* Assign appropriate workstations
* Calculate operation-level time and cost
* Generate Job Cards automatically
* Improve scheduling and planning accuracy
* Maintain consistency in product manufacturing

Routing eliminates guesswork by defining exactly *how* a product should be made.

---

# **3. Routing in Manufacturing Workflow**

Routing provides the connection between:

### ✔ BOM

Defines materials required.

### ✔ Routing

Defines operations and the order of execution.

### ✔ Work Order

Uses routing to generate operational steps.

### ✔ Job Cards

Created for each operation from routing.

### ✔ Plant Floor

Operators execute routing steps in sequence.

### ✔ Costing

Operation time determines labor and machine cost.

Routing is the backbone of the manufacturing execution process.

---

# **4. Routing Structure**

A Routing includes multiple configuration sections describing process sequence and behavior.

---

## **4.1 Basic Details**

| Field                      | Description                                 |
| -------------------------- | ------------------------------------------- |
| **Routing Name**           | Unique identifier for the routing.          |
| **BOM / Item Association** | Optional link to specific BOM or item.      |
| **Description**            | Overview of the manufacturing flow.         |
| **Is Active**              | Indicates if the routing is currently used. |

---

## **4.2 Operation Sequence (Core Section)**

This section defines the ordered list of operations required for manufacturing.

| Field                              | Description                                |
| ---------------------------------- | ------------------------------------------ |
| **Operation Number**               | Sequence number (10, 20, 30…).             |
| **Operation Name**                 | Name of the step (Cutting, Welding, etc.). |
| **Workstation / Workstation Type** | Where the operation occurs.                |
| **Setup Time**                     | Preparation time before operation.         |
| **Run Time / Operation Time**      | Time needed per unit or batch.             |
| **Batch Size**                     | Units processed per cycle.                 |
| **Cycle Time**                     | Time taken for one cycle of production.    |
| **Company**                        | Organization using this routing.           |

The sequence ensures that operations follow a structured, controlled flow.

---

# **5. Routing Example**

A sample routing for a metal fabrication product:

```
Operation 10 – Cutting
Operation 20 – CNC Machining
Operation 30 – Drilling
Operation 40 – Welding
Operation 50 – Grinding
Operation 60 – Painting
Operation 70 – Final Inspection
```

Each of these operations will generate a Job Card inside the Work Order.

---

# **6. Routing Time & Cost Configuration**

Routing impacts cost calculation for finished items.

### ✔ Time-Based Costing

Routing calculates:

* Setup time
* Operation time
* Machine hours
* Labor hours

### ✔ Cost Components

| Cost Component    | Source                                       |
| ----------------- | -------------------------------------------- |
| **Labor Cost**    | Operation or Workstation hourly rate × time. |
| **Machine Cost**  | Machine hourly cost × run time.              |
| **Setup Cost**    | Setup time × setup rate.                     |
| **Overhead Cost** | Based on workstation or operation settings.  |

Routing provides the **actual cost basis** for work orders and products.

---

# **7. Routing and Work Orders**

When a Work Order is created:

1. The system fetches the Routing assigned to the product.
2. It copies all operations into the Work Order.
3. These operations become the Job Card sequence.
4. Operators perform them via Plant Floor.

Routing → Work Order → Job Cards → Execution

This ensures that manufacturing follows the correct step-by-step procedure.

---

# **8. Routing and Multi-Level BOM**

When BOM contains sub-assemblies:

* Each sub-assembly may have its own routing
* Parent item routing drives top-level operations
* Sub-assembly routings generate operations for child Work Orders

This allows complex products to follow multi-step workflows across multiple assemblies.

---

# **9. Routing in Capacity Planning**

Routing determines:

* Total required machine hours
* Total required labor hours
* Load on each workstation
* Sequence dependencies
* Possible bottlenecks

Planning uses:

* Setup Time
* Operation Time
* Workstation capacity
* Number of shifts
* Efficiency and utilization %

Routing is essential for accurate scheduling.

---

# **10. Routing Settings That Influence Production**

Routing may include advanced parameters:

### ✔ Parallel Operations

Multiple operations run simultaneously.

### ✔ Dependent Operations

Next step starts only after previous is completed.

### ✔ QC Required Steps

Routing can force in-process quality checks.

### ✔ Subcontracting

Specific operations can be outsourced.

### ✔ Tooling/Fixture Requirements

Defines required tools per step.

### ✔ Safety Instructions

Ensures compliance and worker safety.

---

# **11. Routing Performance Metrics**

Routing provides critical KPIs for process optimization:

### ✔ Planned vs Actual Time

Compare expected vs actual cycle time.

### ✔ Operation Efficiency

Measure how fast each operation is completed.

### ✔ Machine Utilization

Time workstation spent actively performing routing steps.

### ✔ Rejection Rate per Operation

Helps identify problem areas.

### ✔ Bottleneck Analysis

Find operations causing production delays.

---

# **12. Benefits of Routing**

* Clear and consistent production process
* Accurate cost estimation
* Smooth job scheduling
* Better quality control
* Efficient resource allocation
* Improved reliability of production data
* Ability to identify bottlenecks
* Enhanced operator productivity
* Supports Industry 4.0 shop-floor tracking

---

# **13. When to Create a Routing**

Routing is needed when:

* Your product has more than one operation
* You use multiple workstations/machines
* Each operation has different time or cost
* You want detailed job card tracking
* You need accurate costing
* You want to standardize production
* You need precise operation sequence control