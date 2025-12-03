# 📘 **Operation – Detailed Documentation**

---

# **1. Introduction**

An **Operation** is a specific step or task in the manufacturing process.
It defines **what work needs to be performed**, **where it will be performed**, and **how long it should take**.

Operations are the building blocks of routing and represent each stage required to produce a finished product.
They determine:

* Sequence of manufacturing steps
* Required workstation
* Time and cost estimation
* Job Card creation
* Production progress tracking

---

# **2. Purpose of Operation**

Operations allow manufacturers to:

* Break down production into manageable steps
* Standardize the process for each product
* Assign machine/workstation requirements
* Estimate processing time and cost
* Create Job Cards automatically
* Track progress operation-by-operation
* Ensure accurate routing and workflow

---

# **3. Operations in Manufacturing Workflow**

Operations are used during:

### ✔ Bill of Materials (BOM)

Each BOM references the list of operations required.

### ✔ Routing

Operations define the sequence and workstations for manufacturing.

### ✔ Work Orders

Operations determine how production will be executed.

### ✔ Job Cards

Each Operation generates a Job Card for execution.

### ✔ Plant Floor

Operators perform operations in real time.

### ✔ Costing

Operation time determines labor and machine cost.

---

# **4. Operation Structure**

An Operation contains key configuration data that define HOW the task is performed.

---

## **4.1 Basic Details**

| Field                              | Description                                                     |
| ---------------------------------- | --------------------------------------------------------------- |
| **Operation Name**                 | Name of the task (Cutting, Welding, Drilling, Polishing, etc.). |
| **Operation Description**          | Explanation of what this operation does.                        |
| **Workstation / Workstation Type** | Machine or work area where this operation is executed.          |

---

## **4.2 Time & Scheduling Configuration**

These fields directly impact costing and job scheduling.

| Field                        | Description                                                     |
| ---------------------------- | --------------------------------------------------------------- |
| **Setup Time**               | Time required to prepare machine/tools before operation starts. |
| **Operation Time**           | Time required to process one unit or one batch.                 |
| **Cycle Time**               | Time for each cycle of production (per piece or per batch).     |
| **Batch Size**               | Number of units produced in one cycle.                          |
| **Queue Time (Optional)**    | Time the item waits before the operation starts.                |
| **Teardown Time (Optional)** | Time required after operation finishes.                         |

These values populate work orders and job cards.

---

## **4.3 Costing Configuration**

Operations directly influence cost estimation.

| Cost Component             | Description                                            |
| -------------------------- | ------------------------------------------------------ |
| **Labor Cost**             | Cost of manpower required for the operation.           |
| **Machine Cost**           | Machine running cost based on workstation hourly rate. |
| **Setup Cost**             | Cost related to setup time.                            |
| **Energy / Overhead Cost** | Electricity or overhead cost for the operation.        |

Costs may be inherited from the workstation.

---

## **4.4 Quality & Compliance Settings**

Operations may require inspections or compliance checks:

| Field                      | Description                                      |
| -------------------------- | ------------------------------------------------ |
| **QC Required**            | Indicates if in-process quality check is needed. |
| **QC Template**            | Template defining inspection parameters.         |
| **Safety Instructions**    | Mandatory safety steps workers must follow.      |
| **Special Tools Required** | Tools or jigs required for the operation.        |

---

## **4.5 Documentation & Work Instructions**

Operations may include:

* Work instructions (steps to perform)
* Drawings or design files
* Safety guidelines
* Setup instructions
* Tooling documents

These ensure process consistency on the shop floor.

---

# **5. Operation Flow (Inside a Routing)**

Routing defines the order of operations.

### Example:

```
Operation 10 – Cutting
Operation 20 – CNC Machining
Operation 30 – Drilling
Operation 40 – Assembly
Operation 50 – Inspection
```

The system uses this sequence to:

* Generate Job Cards in order
* Move material through the workstation sequence
* Predict production timelines
* Trigger QC checks
* Track progress step-by-step

---

# **6. Operation Role in Job Cards**

Each operation becomes a job card with:

* Workstation
* Operation time
* Setup time
* Planned vs actual time
* Completed quantities
* Rejection quantities
* Downtime

This enables real-time execution and accurate progress tracking on the Plant Floor.

---

# **7. Operation in Capacity Planning**

Operations influence Planning via:

* Cycle time
* Setup time
* Time per unit
* Workstation availability
* Shift allocation
* Efficiency and utilization

By analyzing operations, planners can detect bottlenecks like:

* Overloaded workstations
* Long-running operations
* Operations exceeding planned capacity

---

# **8. Operation Performance Metrics**

Operations help measure:

### ✔ Planned vs Actual Time

How much time a task was expected to take vs actual time recorded.

### ✔ Operator Efficiency

Performance of workers executing the operation.

### ✔ Machine Utilization

How much machine time was used for the operation.

### ✔ Rejection Rate

QC-related failures per operation.

### ✔ Cycle Time Variability

Difference between standard and actual cycle times.

---

# **9. Integration Points**

| Module                   | Integration Role                                    |
| ------------------------ | --------------------------------------------------- |
| **BOM**                  | Defines which operations apply to a product.        |
| **Routing**              | Organizes operations into a manufacturing sequence. |
| **Work Order**           | Operations form the workflow for manufacturing.     |
| **Workstation**          | Defines where the operation occurs.                 |
| **Job Card**             | Operation executed in real-time.                    |
| **Downtime Entry**       | Logs issues for operations/machines.                |
| **QC / Quality**         | Operation may require QC checks.                    |
| **Production Analytics** | Operation-level time, cost, and rejection analysis. |

---

# **10. Benefits of Using Standard Operations**

* Standardized manufacturing processes
* Accurate product costing
* Improved production planning
* Better workflow control
* Step-by-step visibility and traceability
* Enhanced productivity analysis
* Controlled and consistent output quality
* Reduced operator confusion
* Faster onboarding for new workers

---

# **11. When to Create an Operation**

Create an Operation when:

* A distinct manufacturing step exists
* A separate workstation is required
* Different labor or machine cost applies
* A step requires individual QC
* You want traceability of certain tasks
* Job Cards need to capture time separately
* A process needs monitoring for performance
