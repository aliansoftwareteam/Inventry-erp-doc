# 📘 **Purchase Receipt – Detailed Documentation**

A **Purchase Receipt** is the document used to record the **physical receipt of goods** from a supplier into the warehouse. It updates stock levels by increasing available inventory and confirms that materials have been received as per the purchase order or direct delivery.

Purchase Receipt is central to **procurement, warehouse, quality control, and inventory management**.

---

# **1. Purpose of Purchase Receipt**

A Purchase Receipt is used to:

* Record the arrival of materials from suppliers.
* Update stock levels in warehouses.
* Validate received quantity vs ordered quantity.
* Track partial or complete receipts.
* Support quality inspection workflows.
* Maintain batch/serial number tracking for incoming items.
* Provide an auditable record of inbound stock.
* Allow internal teams to identify material availability for production or sales.

---

# **2. When a Purchase Receipt is Created**

A Purchase Receipt is typically created:

* After receiving goods against a **Purchase Order**.
* When goods arrive without a Purchase Order (if allowed).
* For subcontracted material returns.
* For customer-provided materials (if applicable).
* From drop shipments to internal warehouses (if supported).

### Supports:

✔ Batch Items
✔ Serial Number Items
✔ Partial Receipts
✔ Multiple Warehouses
✔ QC Inspection

---

# **3. Purchase Receipt Workflow Overview**

### **Standard Procurement Workflow**

Purchase Order → Supplier Ships Goods → Purchase Receipt → Quality Inspection (optional)

### **With Quality Inspection**

Purchase Receipt → Quality Inspection → Accepted/Rejected → Materials updated accordingly

### **Without Purchase Order**

Purchase Receipt → Warehouse updates stock
(Used for urgent or unplanned purchases)

### **With Subcontracting**

Subcontract PO → Supplier returns finished goods → Purchase Receipt created for received items

---

# **4. Key Features of Purchase Receipt**

* Increases stock quantity in selected warehouse(s).
* Allows partial receiving of Purchase Orders.
* Tracks batch numbers, serial numbers, and expiry dates.
* Records packaging information.
* Supports multiple warehouses in a single receipt.
* Links with Quality Inspection for controlled acceptance.
* Automatically updates pending procurement quantities.
* Tracks receipt status (Pending, Received, Partially Received, Completed).

---

# **5. Purchase Receipt Form – Detailed Fields**

---

## **5.1 Basic Information**

| Field                   | Description                                            |
| ----------------------- | ------------------------------------------------------ |
| **Supplier**            | Name of the supplier from whom goods are received.     |
| **Purchase Order**      | If linked, item details auto-fetch.                    |
| **Posting Date & Time** | Date and time goods are recorded as received.          |
| **Company**             | Auto-selected based on configuration.                  |
| **Remarks**             | Instructions or notes related to receipt or packaging. |

---

## **5.2 Items Table (Received Materials)**

Each row defines an item being received.

| Field                           | Description                                  |
| ------------------------------- | -------------------------------------------- |
| **Item Code**                   | The received item.                           |
| **Item Name**                   | Auto-fetched for clarity.                    |
| **Quantity**                    | Quantity that arrived at the warehouse.      |
| **UOM**                         | Unit of measure.                             |
| **Received Qty vs Ordered Qty** | Helps track partial deliveries.              |
| **Warehouse**                   | Target warehouse where items will be stored. |
| **Batch No**                    | Required for batch-controlled items.         |
| **Serial Nos**                  | Mandatory for serialized items.              |
| **Rejected Warehouse**          | For storing rejected items (QC failures).    |
| **Description**                 | Additional details of the received item.     |

---

## **5.3 Quality Inspection Fields (Optional)**

| Field                   | Description                                               |
| ----------------------- | --------------------------------------------------------- |
| **Inspection Required** | Indicates whether QC must be completed before acceptance. |
| **Inspection Template** | Defines inspection parameters.                            |
| **Inspection Status**   | Shows accepted or rejected quantities.                    |

If QC is enabled:

* Received items move to temporary “QC Warehouse”.
* Accepted items move to final warehouse.
* Rejected items go to rejection warehouse.

---

## **5.4 Packaging & Logistics Fields**

| Field                     | Description                               |
| ------------------------- | ----------------------------------------- |
| **Transporter / Vehicle** | Information about the shipment transport. |
| **Package Count**         | Number of boxes, pallets, or containers.  |
| **Weight**                | Gross & net weight for inbound shipments. |
| **Delivery Note / LR No** | Supplier’s delivery document reference.   |

---

# **6. Behavior in Stock Operations**

### **6.1 Stock Increase**

Upon submission:

* Stock increases in assigned warehouse.
* Batch/serial numbers entered become available for use.

### **6.2 Partial Completion**

If Purchase Order is not fully received:

* Remaining quantity is tracked.
* Additional receipts can be created later.

### **6.3 Over Receipt (if allowed)**

Some companies allow receiving more than ordered.

* System can warn or block based on settings.

### **6.4 Automatic Updates**

* Delivery status of PO updates automatically.
* Materials become available for Production, Sales, or Internal Requests.

---

# **7. Validations & Rules**

| Rule                                             | Purpose                                          |
| ------------------------------------------------ | ------------------------------------------------ |
| Cannot receive negative or zero qty              | Ensures proper stock data.                       |
| Batch / serial info required for such items      | Maintains traceability.                          |
| Warehouse must be selected                       | Ensures correct stock placement.                 |
| Quantity cannot exceed tolerance (if enabled)    | Prevents over-receiving errors.                  |
| Cannot modify after submission                   | Ensures controlled and auditable stock handling. |
| Reject warehouse required if rejected qty exists | Proper QC segregation.                           |

---

# **8. Status Flow of Purchase Receipt**

| Status                 | Description                               |
| ---------------------- | ----------------------------------------- |
| **Draft**              | Data entered but not yet affecting stock. |
| **Submitted**          | Stock updated; goods officially received. |
| **Partially Received** | PO remains open for remaining items.      |
| **Completed**          | Full PO quantity received.                |
| **Cancelled**          | Receipt reversed, stock removed.          |

---

# **9. Integration with Other Modules**

*(No accounting references included)*

| Module               | Integration Description                                   |
| -------------------- | --------------------------------------------------------- |
| **Purchase Order**   | Auto-fetch items and update pending quantities.           |
| **Quality Module**   | QC inspection triggered if required.                      |
| **Stock Entry**      | Used for internal movement after receipt if needed.       |
| **Material Request** | Satisfies purchase-type material demand.                  |
| **Manufacturing**    | Makes raw materials available for Work Orders.            |
| **Projects**         | Received materials can be tagged to project requirements. |

---

# **10. Example Scenarios**

### 📌 **Scenario 1 – Partial Delivery Against PO**

PO ordered 100 units
Receipt 1 → 60 units
Receipt 2 → 40 units
PO auto-updates delivery status.

---

### 📌 **Scenario 2 – Serial Number Received Items**

Received 5 machines → 5 serial numbers scanned and assigned.

---

### 📌 **Scenario 3 – Batch Items with Expiry**

Received 200 bottles of chemicals → batch created with expiry date.

---

### 📌 **Scenario 4 – QC Inspection Required**

Goods arrive → Purchase Receipt created → QC inspection done →
Accepted items move to Main Warehouse → Rejected items move to Rejection Warehouse.

---

# **11. Summary**

The Purchase Receipt is critical for:

* Updating stock when goods arrive
* Managing quality inspections
* Handling batch/serial requirements
* Ensuring accurate warehouse inventory
* Supporting procurement and production operations

It plays a vital role in inbound logistics and stock accuracy.

---