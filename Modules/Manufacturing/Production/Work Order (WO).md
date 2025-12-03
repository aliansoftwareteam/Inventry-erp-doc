# 📘 **Work Order – Detailed Documentation**

---

# **1. Introduction**

A **Work Order** is the central document used to manage the manufacturing of a product.
It defines *what to produce*, *how much to produce*, *which routing to follow*, *which materials are required*, and *which workstations will be used*.

Work Orders connect **Production Planning**, **BOM**, **Routing**, **Shop Floor Execution**, and **Inventory** into a single flow.

---

# **2. Purpose of Work Order**

A Work Order is used to:

* Convert production plans into executable manufacturing tasks
* Reserve materials needed for production
* Track WIP (Work in Progress)
* Record time, labor, machine usage
* Manage operation-level job cards
* Capture actual material consumption
* Receive finished goods into inventory
* Measure efficiency, cost, and variances

---

# **3. Work Order Lifecycle**

Below is the typical lifecycle of a Work Order:

```
1. Create Work Order
2. Review Required Materials
3. Issue Materials (Stock Entry)
4. Start Operations (Job Cards / Plant Floor)
5. Track Production Progress
6. In-Process Quality Checks
7. Complete Operations
8. Receive Finished Goods to Stock
9. Close Work Order
```

---

# **4. Work Order Fields & Structure**

A Work Order contains multiple sections. Below is a detailed explanation of each one.

---

## **4.1 Basic Details**

| Field                          | Description                                                 |
| ------------------------------ | ----------------------------------------------------------- |
| **Work Order ID**              | Unique identifier for the work order.                       |
| **Item to Manufacture**        | Product to be produced; must have a valid BOM.              |
| **Quantity to Manufacture**    | Total quantity required for production.                     |
| **Production Plan (Optional)** | If created from a production plan, it links to that source. |
| **Planned Start Date**         | Suggested date for starting production.                     |
| **Planned End Date**           | Planned completion date.                                    |
| **Company**                    | Organization owning the work order.                         |

---

## **4.2 BOM & Routing Section**

| Component             | Description                                                                       |
| --------------------- | --------------------------------------------------------------------------------- |
| **Bill of Materials** | Defines materials and operations needed for manufacturing.                        |
| **BOM Version**       | Version of BOM used for this work order.                                          |
| **Routing**           | Sequence of operations that will be executed.                                     |
| **Operations List**   | Auto-fetched from routing: includes operation name, work center, cycle time, etc. |

---

## **4.3 Material Requirements**

The system fetches all materials from the BOM and calculates:

* Required quantity
* Available stock
* Shortage quantity
* Reserved stock
* Warehouse from which material will be issued

Fields:

| Field                      | Description                                    |
| -------------------------- | ---------------------------------------------- |
| **Required Material List** | Components needed for production based on BOM. |
| **Total Required Qty**     | Required = BOM Qty × WO Qty.                   |
| **Available Qty**          | Current stock in selected warehouse.           |
| **Shortage Qty**           | Indicates materials missing from stock.        |
| **Material Reservation**   | Reserves stock for the work order.             |

---

## **4.4 Operations & Job Cards**

Work Order operations define how manufacturing will occur.

| Field              | Description                                         |
| ------------------ | --------------------------------------------------- |
| **Operation Name** | Individual task (Cutting, Assembly, Welding, etc.). |
| **Workstation**    | Machine/area where the operation will be performed. |
| **Planned Time**   | Estimated time required for the operation.          |
| **Setup Time**     | Time required to prepare the workstation.           |
| **Cycle Time**     | Time to produce one unit.                           |
| **Completed Qty**  | Quantity completed per operation.                   |
| **Job Card**       | Generated to record operation-level work.           |

---

## **4.6 Quality Control**

Depending on your system, QC may occur:

* After specific operations
* After WIP transfer
* After final production

Fields:

| Field                | Description                        |
| -------------------- | ---------------------------------- |
| **QC Required**      | Indicates if inspection is needed. |
| **QC Template**      | Predefined inspection parameters.  |
| **Pass/Fail Status** | Quality result of inspection.      |

---

## **4.7 Finished Goods Receipt**

When production is completed:

| Field                         | Description                                            |
| ----------------------------- | ------------------------------------------------------ |
| **Finished Good Qty**         | Quantity produced.                                     |
| **Warehouse**                 | Finished goods warehouse where items will be received. |
| **Stock Entry (Manufacture)** | Auto-created stock movement for finished goods.        |

---

## **4.8 Costing Section**

Work Order costing includes:

* Material Cost (actual consumed materials)
* Operation Cost (labor + machine time)
* Overhead Cost
* Additional Charges
* Variance (Standard vs Actual)

Fields:

| Field                 | Description                                            |
| --------------------- | ------------------------------------------------------ |
| **Planned Cost**      | Cost based on BOM and routing.                         |
| **Actual Cost**       | Actual cost after production.                          |
| **Material Variance** | Difference between planned vs actual material usage.   |
| **Time Variance**     | Difference between expected vs actual production time. |
| **Cost Variance**     | Final variance after production.                       |

---

# **5. Work Order Actions**

| Action                        | Purpose                                               |
| ----------------------------- | ----------------------------------------------------- |
| **Create**                    | Create a new WO from scratch or from Production Plan. |
| **Material Request**          | Raise purchase/transfer requests for shortages.       |
| **Start/Complete Operations** | Track progress for each operation.                    |
| **Issue Materials**           | Create stock entry to send materials to WIP.          |
| **Receive Finished Goods**    | Post-production entry to add FG into warehouse.       |
| **Close Work Order**          | Marks the WO as fully completed.                      |

---

# **6. Integration Points**

Work Order interacts with:

| Module              | Integration Description                         |
| ------------------- | ----------------------------------------------- |
| **BOM**             | Fetches material and routing details.           |
| **Routing**         | Determines operation sequence.                  |
| **Workstations**    | Defines machine capacity and time.              |
| **Inventory**       | Adjusts stock during issue and receipt.         |
| **Quality Control** | In-process or final inspection.                 |
| **Costing**         | Calculates standard and actual production cost. |

---

# **7. Work Order Status Flow**

```
Draft  
↓  
Submitted  
↓  
Material Issued  
↓  
In Production  
↓  
Partially Completed  
↓  
Completed  
↓  
Closed
```

---

# **8. Benefits of Using Work Orders**

* Accurate production execution
* Real-time progress visibility
* Better material planning
* Reduced stock-out issues
* Effective labor/machine tracking
* Accurate costing and variance detection
* Compliance with standard manufacturing processes