
# 📘 **Downtime Entry – Detailed Documentation**

---

# **1. Introduction**

A **Downtime Entry** is used to record any period during which a machine, workstation, or production line is **not operational**.
Downtime may be planned (maintenance) or unplanned (breakdown).

Downtime Entry allows manufacturers to track:

* Production delays
* Machine performance
* Maintenance requirements
* Root causes of inefficiency
* OEE (Overall Equipment Efficiency)

It is essential for ensuring accurate shop-floor monitoring and productivity optimization.

---

# **2. Purpose of Downtime Entry**

Downtime Entry is used to:

* Capture when a machine stops working
* Log the reason and duration of downtime
* Measure machine utilization
* Identify bottlenecks in production
* Support maintenance planning
* Improve OEE and operational efficiency
* Analyze repetitive issues

---

# **3. When Downtime Entry Is Created**

Downtime entries can be created in different situations:

### ✔ **1. Machine breakdown**

Mechanical or electrical failures.

### ✔ **2. Unplanned stoppage**

Operator absence, material shortage, tool unavailability, etc.

### ✔ **3. Planned maintenance**

Preventive maintenance, cleaning, calibration.

### ✔ **4. Setup or changeover time**

Switching from one product to another.

### ✔ **5. External factors**

Power failure, safety issues, inspection holds.

---

# **4. Downtime Entry Structure**

A Downtime Entry consists of the following key components:

---

## **4.1 Basic Details**

| Field                     | Description                                  |
| ------------------------- | -------------------------------------------- |
| **Downtime Entry ID**     | Unique identifier for the downtime log.      |
| **Workstation**           | Machine or area where the downtime occurred. |
| **Work Order (Optional)** | If downtime affected a specific Work Order.  |
| **Job Card (Optional)**   | If downtime occurred during an operation.    |
| **Company**               | Company associated with the entry.           |

---

## **4.2 Time Tracking**

| Field                       | Description                                        |
| --------------------------- | -------------------------------------------------- |
| **Start Time**              | Time when downtime began.                          |
| **End Time**                | Time when downtime ended.                          |
| **Total Downtime Duration** | Auto-calculated total duration (in minutes/hours). |
| **Shift**                   | Shift during which the downtime occurred.          |

---

## **4.3 Downtime Reasoning**

| Field                   | Description                                                                 |
| ----------------------- | --------------------------------------------------------------------------- |
| **Downtime Reason**     | Predefined reason such as breakdown, changeover, shortage, inspection, etc. |
| **Downtime Category**   | Planned / Unplanned.                                                        |
| **Description / Notes** | Additional details explaining the issue.                                    |

Examples of downtime reasons:

* Machine Breakdown
* Preventive Maintenance
* Tool Change
* Material Shortage
* Quality Hold
* Operator Break
* Power Failure

---

## **4.4 Impact Details**

| Field                          | Description                        |
| ------------------------------ | ---------------------------------- |
| **Affected Operation**         | Operation halted due to downtime.  |
| **Impact on Quantity**         | Units affected or delayed.         |
| **Additional Cost (Optional)** | Cost associated with downtime.     |
| **Resource Lost**              | Machine hours or labor hours lost. |

---

# **5. Workflow of Downtime Entry**

A typical downtime workflow:

```
Machine Stops
     ↓
Operator/Maintenance Logs Downtime
     ↓
Supervisor Reviews Entry
     ↓
Downtime Duration Is Calculated
     ↓
Reason and Category Are Assigned
     ↓
Maintenance or Corrective Action Taken
     ↓
Entry Closed
```

---

# **6. Downtime in Manufacturing Execution**

Downtime Entry is integrated with:

* **Job Cards**
* **Work Orders**
* **Plant Floor dashboards**
* **Workstations**
* **Maintenance system**

### Example scenario:

1. Operator starts Job Card.
2. Machine breaks during cutting operation.
3. Operator logs a Downtime Entry.
4. Job Card timer stops temporarily.
5. Maintenance team fixes machine.
6. Job Card continues.
7. Downtime reflects in the production report.

---

# **7. Downtime Categories**

| Category             | Description                                           |
| -------------------- | ----------------------------------------------------- |
| **Planned**          | Maintenance, cleaning, calibration, scheduled breaks. |
| **Unplanned**        | Breakdowns, material shortages, operator issues.      |
| **Minor Stoppage**   | Short delays under a threshold (e.g., <10 minutes).   |
| **Setup/Changeover** | Time taken to prepare for new production run.         |

---

# **8. Downtime Metrics & Analysis**

Downtime Entries allow companies to measure:

### ✔ **Total Downtime Hours**

Total amount of machine stoppage.

### ✔ **Downtime Frequency**

How often downtime occurs per machine/shift.

### ✔ **MTTR (Mean Time To Repair)**

Average time to fix a breakdown.

### ✔ **MTBF (Mean Time Between Failures)**

Average running time before breakdown happens.

### ✔ **OEE Loss Analysis**

Downtime reduces:

* **Availability**
* **Performance**
* **Output Quantity**

---


# **9. Benefits of Downtime Entry**

* Improves machine utilization
* Helps identify bottlenecks
* Enables preventive maintenance
* Reduces unexpected stoppages
* Strengthens production planning accuracy
* Supports better OEE monitoring
* Enhances root cause analysis
* Reduces production delays

---

# **10. When to Use Downtime Entry**

You should create a Downtime Entry when:

* A machine stops unexpectedly
* The job cannot proceed due to external factors
* Maintenance is required
* A shift changeover or tool setup delays production
* A QC hold stops the process

---

# **11. Integration Points**

Downtime Entry integrates with the following modules:

| Module                   | Role                                               |
| ------------------------ | -------------------------------------------------- |
| **Work Order**           | Records downtime affecting execution timelines.    |
| **Job Card**             | Pauses operation-level time tracking.              |
| **Workstation**          | Tracks performance and reliability.                |
| **Maintenance**          | Generates maintenance tasks from downtime reasons. |
| **Production Analytics** | Includes downtime in productivity KPIs.            |

