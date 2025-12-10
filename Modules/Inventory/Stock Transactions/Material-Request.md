# 📘 **Material Request – Detailed Documentation**

A **Material Request** is an internal document used to request materials for various purposes such as **purchase, production, stock transfer, or internal consumption**.
It acts as the starting point for procurement and material planning workflows within the organization.

Material Requests ensure controlled, traceable, and organized movement or acquisition of materials.

---

# **1. Purpose of Material Request**

A Material Request is used to:

* Request purchase of items.
* Request material transfer between warehouses.
* Request issue of materials for consumption.
* Plan material requirement for manufacturing.
* Maintain proper demand documentation.
* Prevent unauthorized stock movement.
* Drive internal workflows for approval and fulfillment.

---

# **2. Types of Material Requests**

Different types of Material Requests serve different operational needs:

| Type                  | Purpose                                                                 |
| --------------------- | ----------------------------------------------------------------------- |
| **Purchase**          | For procuring new materials from suppliers.                             |
| **Material Transfer** | For moving materials between warehouses.                                |
| **Material Issue**    | For issuing materials to departments or internal use.                   |
| **Manufacture**       | For generating demand for production (used in Manufacturing workflows). |
| **Customer Provided** | For materials provided by customers for subcontracting or job work.     |

---

# **3. Workflow Overview**

Below is the general workflow depending on the request type:

### **A. Purchase Request Workflow**

Material Request → Supplier Quotation (optional) → Purchase Order → Purchase Receipt

### **B. Material Transfer Workflow**

Material Request → Stock Entry (Material Transfer) → Delivery from Source → Receipt at Target Warehouse

### **C. Material Issue Workflow**

Material Request → Stock Entry (Material Issue) → Consumption posted

### **D. Manufacture Request Workflow**

Material Request → Production Plan → Work Order → Manufacturing Execution

Material Requests act as a **trigger** document for downstream processes.

---

# **4. Key Use Cases**

* Production department requesting raw materials.
* Stores department requesting transfer of stock.
* Office/admin requesting stationary or consumables.
* Project team requesting materials for project sites.
* Engineering team raising manufacturing demand.
* Warehouse replenishment between locations.

---

# **5. Material Request Form – Detailed Fields**

Below is a detailed explanation of fields typically available in a Material Request.

---

## **5.1 Basic Information**

| Field                         | Description                                                                  |
| ----------------------------- | ---------------------------------------------------------------------------- |
| **Material Request Type**     | Defines the purpose of the request (Purchase, Transfer, Issue, Manufacture). |
| **Transaction Date**          | Date when the request is created.                                            |
| **Required Date**             | When the material is needed.                                                 |
| **Department / Requested By** | The department or person requesting the material.                            |
| **Company**                   | Auto-selected based on configuration.                                        |

---

## **5.2 Items Table (Material Details)**

Each row represents an item needed.

| Field             | Description                                                           |
| ----------------- | --------------------------------------------------------------------- |
| **Item Code**     | The item being requested.                                             |
| **Item Name**     | Auto-fetched item name.                                               |
| **Quantity**      | Quantity required for the request.                                    |
| **UOM**           | Unit of Measure of the item.                                          |
| **Warehouse**     | Warehouse from where stock will be issued or to where it is required. |
| **Schedule Date** | Planned date for availability.                                        |
| **Description**   | Additional notes on the requested item.                               |

---

## **5.3 Warehouse Settings**

Depending on the request type:

### **Purchase Request**

* Only **Target Warehouse** is needed where items will be received.

### **Material Transfer**

* **Source Warehouse** → from where items are moved
* **Target Warehouse** → where items are delivered

### **Material Issue**

* Only **Source Warehouse** (for consumption)

### **Manufacture**

* Warehouse is determined by production settings but can be overridden.

---

## **5.4 Planning & Priority Fields**

| Field                     | Description                                               |
| ------------------------- | --------------------------------------------------------- |
| **Priority**              | Normal / Urgent / High – used for internal planning.      |
| **Project / Cost Center** | Used to group material requests by project or department. |
| **Purpose / Remarks**     | Optional remarks to clarify purpose of material.          |

---

# **6. Behavior in Stock & Procurement Processes**

### **6.1 Reservation of Stock**

If enabled, system can reserve available stock for the request.

### **6.2 Triggering Purchase Orders**

For Purchase Type:

* A Purchase Order can be created directly from the Material Request.
* Useful for procurement teams to convert demand into PO.

### **6.3 Triggering Stock Entry**

For Transfer or Issue:

* Stock Entry is created directly for fulfilling the request.
* Ensures accurate documentation of stock movement.

### **6.4 Manufacturing Planning**

For Manufacture Type:

* System considers this Material Request in Production Plans.
* Generates Work Orders and calculates raw material requirement.

---

# **7. Validations & Rules**

| Rule                                                  | Why It Exists                                                  |
| ----------------------------------------------------- | -------------------------------------------------------------- |
| Requested quantity must be positive                   | Prevents incorrect demand creation.                            |
| Required Date cannot be before Transaction Date       | Ensures logical planning.                                      |
| Item must be active and valid                         | Prevents obsolete or incorrect materials from being requested. |
| Source warehouse must have stock (for Transfer/Issue) | Prevents negative stock errors.                                |
| Cannot modify submitted requests unless cancelled     | Ensures audit and traceability.                                |

---

# **8. Material Request Status Flow**

Typical statuses include:

| Status                         | Meaning                                     |
| ------------------------------ | ------------------------------------------- |
| **Draft**                      | Request is being prepared.                  |
| **Pending**                    | Waiting for approval (if workflow enabled). |
| **Partially Ordered / Issued** | Only a portion is fulfilled.                |
| **Ordered / Issued**           | Fully acted upon.                           |
| **Stopped**                    | Request halted.                             |
| **Cancelled**                  | Request is void.                            |

---

# **9. Example Scenarios**

### 📌 **Scenario 1 – Production Raw Material Shortage**

Production team raises a **Manufacture** Material Request → triggers Production Plan → generates Work Orders.

### 📌 **Scenario 2 – Warehouse Replenishment**

Store team raises **Material Transfer** request → stock moved from Central Warehouse to Branch Warehouse.

### 📌 **Scenario 3 – Purchase Requirement**

Admin raises **Purchase** Material Request for stationary → procurement converts MR to Purchase Order.

### 📌 **Scenario 4 – Consumption**

Maintenance team raises a **Material Issue** request for tools → Stock Entry (Material Issue) is created.

---

# **10. Summary**

Material Request is a foundational document in inventory and manufacturing operations that:

* Captures demand for materials
* Controls stock movement
* Supports procurement and planning
* Enhances warehouse coordination
* Enables smooth manufacturing workflows
* Does **not** involve accounting (per your requirement)

---