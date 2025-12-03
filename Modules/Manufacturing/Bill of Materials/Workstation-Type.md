# 📘 **Workstation Type – Detailed Documentation**

---

# **1. Introduction**

A **Workstation Type** is a classification used to group similar workstations under a common category.
While a *workstation* represents an **actual machine or physical work area**, a **workstation type** defines the **category or class** of such machines.

It is used to control:

* Capacity planning
* Machine behavior rules
* Costing configuration
* Operational categorization
* Reporting and analytics

Workstation Types help standardize the structure of production resources.

---

# **2. Purpose of Workstation Type**

Workstation Types serve to:

* Categorize machines/work areas
* Standardize settings for all workstations under the same type
* Simplify routing and operation assignment
* Improve production planning accuracy
* Support costing and efficiency calculations
* Provide grouped reporting for machines

---

# **3. Role of Workstation Type in Manufacturing**

Workstation Type provides a **top-level classification**. For example:

| Workstation Type     | Example Workstations             |
| -------------------- | -------------------------------- |
| **CNC Machines**     | CNC-01, CNC-02, CNC-03           |
| **Cutting Machines** | Cutter-A, Cutter-B               |
| **Assembly Line**    | Assembly Line 1, Assembly Line 2 |
| **Welding Stations** | Welding Booth 1, Welding Booth 2 |

Workstation Type ensures consistent configuration across similar machines.

---

# **4. Workstation Type Structure**

A Workstation Type contains multiple configuration fields that apply to every workstation under it.

---

## **4.1 Basic Details**

| Field                     | Description                                                           |
| ------------------------- | --------------------------------------------------------------------- |
| **Workstation Type Name** | The category name (e.g., CNC Machine, Manual Station, Assembly Line). |
| **Description**           | Optional description of the category.                                 |
| **Is Active**             | Indicates if this category is still used.                             |

---

## **4.2 Standard Cost Configuration**

Workstation Type defines default cost values which can be inherited by workstations:

| Cost Component                      | Description                                         |
| ----------------------------------- | --------------------------------------------------- |
| **Operating Cost per Hour**         | Machine cost allocated per hour of use.             |
| **Labor Cost per Hour**             | Standard labor cost for operations under this type. |
| **Energy/Overhead Cost (Optional)** | Additional hourly overheads like electricity.       |

These defaults can be overridden at workstation level.

---

## **4.3 Capacity & Efficiency Settings**

| Field                                 | Description                               |
| ------------------------------------- | ----------------------------------------- |
| **Working Hours per Day**             | Standard number of operating hours.       |
| **Efficiency (%)**                    | Expected productive efficiency (ex: 90%). |
| **Utilization (%)**                   | Target machine utilization.               |
| **Queue Time / Wait Time (Optional)** | Time before/after operations.             |

These factors impact capacity planning and implementation.

---

# **5. Workstation Type vs Workstation**

| Aspect         | Workstation Type                          | Workstation                                  |
| -------------- | ----------------------------------------- | -------------------------------------------- |
| **Definition** | A category of machines/work areas         | A specific physical machine or work area     |
| **Purpose**    | Standardization and grouping              | Actual machine used in production            |
| **Attributes** | Cost rates, efficiency, capacity defaults | Real-time availability, downtime, scheduling |
| **Used In**    | Routing templates, BOM defaults, planning | Job Cards, WOs, Plant Floor execution        |

Workstation Type creates a **top-down hierarchy** that makes management easier.

---

# **6. Workstation Type in Routing**

Workstation Types can be used when setting up operations.

### Example Routing Setup:

| Operation     | Workstation Type |
| ------------- | ---------------- |
| Cutting       | Cutting Machine  |
| CNC Machining | CNC Machine      |
| Welding       | Welding Station  |

When creating a new workstation under a type:

* It automatically inherits default cost/time settings
* Routing steps naturally align with workstation capabilities

---

# **7. Workstation Type in Capacity Planning**

During planning, the system evaluates:

* Total hours available for each workstation type
* Expected load from all operations
* Bottlenecks based on workstation type capacity

This helps estimate:

* Required machines
* Shift planning
* Production scheduling
* Operation balancing

---

# **8. Workstation Type in Costing**

Costing for operations can be derived from:

### ✔ Workstation Type Defaults

If workstation-specific cost is not defined.

### ✔ Workstation Actual Cost

If workstation has specific cost setup.

This helps in:

* Standard costing
* Actual costing
* Cost variance analysis
* Budgeting & forecasting

---

# **9. Workstation Type Settings in System Behavior**

Workstation Type can control:

* Whether setup time applies
* Whether machine needs calibration before use
* Whether downtime is allowed/recorded
* Whether it is a batch-based or unit-based operation
* Preferred shift or production window

These settings streamline operation planning.

---

# **10. Benefits of Workstation Type**

* Ensures standardization across machines
* Simplifies workstation creation
* Reduces redundancy in configuration
* Improves routing efficiency
* Enhances costing accuracy
* Enables grouped reporting
* Supports capacity planning
* Improves maintenance and downtime visibility

---

# **11. When to Use Workstation Types**

Workstation Types are essential when:

* You have multiple machines of the same category
* You want standardized cost and capacity values
* You manage hundreds of workstations
* You need grouped reporting for analysis
* You perform batch planning and scheduling

---

# **12. Integration Points**

Workstation Type integrates with:

| Module                     | Role                                          |
| -------------------------- | --------------------------------------------- |
| **Workstation**            | Inherits settings from workstation type.      |
| **Operation / Routing**    | Assigns type-level operation mapping.         |
| **Work Orders**            | Select workstation based on type.             |
| **Job Cards**              | Tracks performance per machine category.      |
| **Maintenance / Downtime** | Categorizes machine issues by type.           |
| **Production Analytics**   | Aggregates OEE and utilization at type level. |

