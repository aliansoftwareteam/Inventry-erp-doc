
# 📘 **Job Card – Overview Document**

---

# **1. Introduction**

A **Job Card** is an operation-level execution document used on the shop floor.
It tells operators **what operation to perform**, **which workstation to use**, and **how much quantity to process**.
It acts as the **bridge between the Work Order and shop-floor workers**.

Job Cards ensure that every production operation is tracked accurately for **time, labor, machine usage, progress, and quality**.

---

# **2. Purpose of a Job Card**

A Job Card is used to:

* Communicate operation instructions to workers
* Track production progress at each operation
* Capture start & finish times
* Record machine downtime or delays
* Capture actual labor and machine hours
* Update the quantity completed at each step
* Maintain traceability from start to finish

---

# **3. How Job Cards Work**

A Job Card is generated from a **Work Order**, for each operation defined in the BOM/Routing.

Typical process:

```
Work Order → Operations (Routing) → Generate Job Cards → Execute → Complete Operation
```

Each operation of the routing may have its own Job Card.

---

# **4. Key Components of a Job Card**

A Job Card contains the essential details required to execute a specific operation:

| Component                     | Overview                                                        |
| ----------------------------- | --------------------------------------------------------------- |
| **Operation**                 | The specific step (e.g., Cutting, Welding, Assembly).           |
| **Workstation**               | Machine or work center where the operation will be carried out. |
| **Planned Time**              | Expected time for the operation.                                |
| **Start Time / End Time**     | Actual time taken by the operator.                              |
| **Operator / Worker**         | Person performing the job.                                      |
| **Completed Qty**             | Quantity processed during this operation.                       |
| **Rejected Qty**              | Quantity rejected or failed QC.                                 |
| **Materials Used (Optional)** | Raw material or sub-components consumed.                        |
| **Status**                    | Pending → In Progress → Completed.                              |

---

# **5. What Operators Do With a Job Card**

Operators use the Job Card for:

* Seeing operation instructions
* Starting and stopping the operation
* Reporting completed quantity
* Logging downtime or machine issues
* Recording time taken
* Tracking partial completion
* Submitting the job when done

Many systems allow this through:

* **Plant Floor dashboard**
* **Tablet/mobile devices on the shop floor**
* **Barcode/QR scanning of Job Card**

---

# **6. Job Card Status Flow**

```
Pending  
↓  
In Progress  
↓  
Partially Completed (Optional)  
↓  
Completed  
↓  
Submitted / Closed
```

---

# **7. Job Card in Manufacturing Workflow**

Job Cards sit between Work Orders and Finished Goods.

```
Work Order  
    ↓  
Generate Job Cards  
    ↓  
Operator Executes Operation  
    ↓  
Update Progress & Time  
    ↓  
Operation Completed  
    ↓  
Next Operation / QC 
```

Job Cards ensure each operation is **accurately recorded** before final production is completed.

---

# **8. Benefits of Job Cards**

* Clear instructions for workers
* Accurate tracking of time and efficiency
* Real-time shop-floor visibility
* Traceability of each operation
* Helps identify delays, bottlenecks, or machine issues
* Supports costing by recording labor and machine hours
* Improves production planning accuracy
* Ensures accountability for each operation

---

# **9. When Job Cards Are Essential**

Use Job Cards when:

* Multiple operations exist in production
* You need detailed shop-floor tracking
* Labor or machine costing matters
* There are high chances of errors if steps are skipped
* You want to measure efficiency at each workstation
* You require traceability for quality audits

---

# **10. Job Card Integration Points**

| Module                   | Role                                            |
| ------------------------ | ----------------------------------------------- |
| **Work Order**           | Source document for Job Card creation.          |
| **BOM & Routing**        | Defines the operation sequence and workstation. |
| **Workstation**          | Machine where the job runs.                     |
| **Quality Control**      | In-process QC checks may be triggered.          |
| **Inventory**            | Tracks consumed materials if required.          |
| **Production Analytics** | Uses Job Card data to generate KPIs.            |

---