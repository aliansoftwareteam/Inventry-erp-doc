# 📘 **Plant Floor – Detailed Documentation**

---

# **1. Introduction**

The **Plant Floor** (also known as Shop Floor Interface) is the real-time operational dashboard used by machine operators, supervisors, and production managers to:

* Track ongoing production
* Execute job cards
* Log start/stop times
* Record completed quantities
* Report downtime
* Monitor machine/workstation status
* Manage shift-level production activity

It serves as the **single interface connecting people on the shop floor with the digital production system**.

---

# **2. Purpose of Plant Floor**

The Plant Floor is used to:

* View all assigned operations for workers
* Start/stop jobs in real time
* Log production quantity and rejects
* Record machine downtime
* Provide real-time visibility of shop-floor performance
* Optimize production flow
* Improve accuracy of time, labor, and machine cost tracking
* Reduce manual paperwork and human error

Its primary goal is to **streamline manufacturing execution**.

---

# **3. Key Features of Plant Floor**

The Plant Floor screen offers several powerful capabilities:

### ✔ **Real-Time Job Execution**

Operators can start, pause, and complete operations.

### ✔ **Workstation Status Tracking**

Shows whether machines are:

* Available
* Running
* Idle
* Under Maintenance
* In Breakdown

### ✔ **Job Queue Visibility**

Lists all pending tasks for operators or workstations.

### ✔ **Time Logging**

Automatically captures:

* Operation start time
* End time
* Actual cycle time
* Total machine hours
* Operator work hours

### ✔ **Downtime Reporting**

Operators can log:

* Breakdown
* Tool change
* Material shortage
* QC hold

### ✔ **Quantity Reporting**

Workers can record:

* Completed quantity
* Rejected quantity
* Partially processed quantity

### ✔ **Shift-Based Execution**

Supports multiple shifts with real-time progress.

---

# **4. Plant Floor Interface Structure**

A Plant Floor screen typically contains the following sections:

---

## **4.1 Assigned Jobs Section**

Shows all operations assigned to:

* A specific operator
* A workstation
* A department
* A shift

Displays:

| Field                 | Description                                       |
| --------------------- | ------------------------------------------------- |
| **Job Card**          | Operation number and task details.                |
| **Work Order**        | Main order associated with the job.               |
| **Operation**         | Current step (Cutting, Drilling, Assembly, etc.). |
| **Workstation**       | Machine assigned for the operation.               |
| **Planned Time**      | Expected duration of the operation.               |
| **Required Quantity** | Quantity to be produced.                          |

---

## **4.2 Active Job Display**

When an operator starts a job, a dedicated panel shows:

| Component                    | Purpose                                |
| ---------------------------- | -------------------------------------- |
| **Timer (Running)**          | Shows operation duration in real time. |
| **Start/Pause/Stop Buttons** | Control job execution.                 |
| **Operator Details**         | Tracks who is performing the task.     |
| **Quantity Fields**          | Enter completed and rejected qty.      |
| **Operation Instructions**   | Any specific notes or guidance.        |

---

## **4.3 Machine/Workstation Panel**

Shows the real-time status of the workstation:

| Status          | Meaning                                 |
| --------------- | --------------------------------------- |
| **Running**     | Job card currently in progress.         |
| **Idle**        | No job is running despite availability. |
| **Breakdown**   | Machine is stopped due to downtime.     |
| **Maintenance** | Under scheduled work or repair.         |
| **Blocked**     | Cannot operate due to a condition.      |

This data is automatically updated when the operator logs downtime or completes the job.

---

## **4.4 Downtime Logging**

Operators can report issues directly from the Plant Floor:

Fields:

* Downtime Reason
* Start Time
* End Time
* Description
* Machine Issue Category
* Maintenance Required (Yes/No)

This reduces delays and improves visibility for supervisors.

---

## **4.5 Quantity Reporting Panel**

Operators log:

| Field                  | Description                 |
| ---------------------- | --------------------------- |
| **Completed Quantity** | How many units finished.    |
| **Rejected Quantity**  | Units failed in QC.         |
| **WIP Quantity**       | Partially completed parts.  |
| **Rejection Reason**   | Reason for non-conformance. |

Once submitted, the system updates the Job Card and Work Order.

---

# **5. Plant Floor Workflow**

```
Jobs Assigned → Operator Views on Plant Floor
       ↓
Start Job  → Timer Begins
       ↓
Perform Operation
       ↓
Record Quantity (Completed / Rejected)
       ↓
Log Downtime (If Occurs)
       ↓
End Job → Timer Stops
       ↓
Submit for Next Operation / QC
```

---

# **6. Role of Plant Floor in Manufacturing Execution**

Plant Floor connects all critical modules:

| Module                   | How It Connects                                   |
| ------------------------ | ------------------------------------------------- |
| **Work Order**           | Provides operations and routing.                  |
| **Job Card**             | Executed and updated through Plant Floor.         |
| **Workstation**          | Real-time status updates and machine usage logs.  |
| **Downtime Entry**       | Logged directly by operators.                     |
| **Quality Control**      | Supports in-process QC checks.                    |
| **Inventory**            | Updates material consumption (optional).          |
| **Production Analytics** | Feeds data for OEE, utilization, efficiency KPIs. |

---

# **7. Benefits of Using Plant Floor**

* Live monitoring of production
* Eliminates manual job sheets
* Increased production accuracy
* Better utilization of machines
* Real-time operator accountability
* Faster issue detection (breakdown, QC hold, material shortage)
* Higher transparency in operations
* Data-driven decisions from accurate machine/operation logs
* Improved shop-floor discipline

---

# **8. Plant Floor Data Used for KPIs**

Plant Floor feeds critical data for:

### ✔ OEE (Overall Equipment Efficiency)

* Availability
* Performance
* Quality

### ✔ Efficiency & Utilization

* Machine run hours
* Idle time
* Downtime

### ✔ Labor Productivity

* Operation time vs ideal time
* Operator efficiency

### ✔ Production KPIs

* Actual vs planned quantity
* Rejection rates
* Cycle time variance

---

# **9. When to Use Plant Floor**

Plant Floor is essential when:

* Multiple workstations/machines run operations
* You need real-time visibility of production
* Manual data entry causes delays or errors
* Production execution requires strict tracking
* You want to implement Industry 4.0 practices
* OEE and downtime analysis is required

---

# **10. Integration Points**

| Module                   | Role                                              |
| ------------------------ | ------------------------------------------------- |
| **Job Card**             | Core execution document used on Plant Floor.      |
| **Workstation**          | Real-time machine status tracking.                |
| **Downtime Entry**       | Direct logging from shop floor.                   |
| **Work Order**           | Tracks operation completion.                      |
| **Quality**              | In-process inspection trigger.                    |
| **Inventory**            | Material updates (optional).                      |
| **Production Analytics** | Uses Plant Floor data for performance dashboards. |
