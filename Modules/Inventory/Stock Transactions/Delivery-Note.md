# 📘 **Delivery Note – Detailed Documentation**

A **Delivery Note** is a document used to record the **outward movement of goods** from the organization to a customer, project site, internal location, or any delivery destination.
It updates stock levels by reducing inventory from the source warehouse and ensures accurate tracking of dispatched items.

Delivery Note is a key document in **Sales, Logistics, Warehouse, and Inventory** operations.

---

# **1. Purpose of Delivery Note**

The Delivery Note is used to:

* Record the physical delivery of items to customers.
* Reduce stock quantities from the warehouse.
* Track partial or complete delivery against a Sales Order.
* Manage logistics, packaging, and dispatch operations.
* Validate that the correct items and quantities are shipped.
* Support packing, picking, and delivery trip workflows.
* Maintain traceability of outbound stock with Serial/Batch tracking.

It acts as the official document for dispatch operations.

---

# **2. When Delivery Note is Used**

A Delivery Note is typically created:

* After confirming a **Sales Order**.
* When dispatching goods directly without a Sales Order (if allowed).
* For internal transfers between locations (if used for logistics only).
* For project deliveries.
* For delivering bundled products (expanded into individual components).
* When serial/batch-controlled items need movement tracking.

It ensures accurate and controlled outbound stock movement.

---

# **3. Delivery Note Workflow Overview**

### **Standard Workflow**

Sales Order → Pick List (optional) → Delivery Note → Dispatch → Customer Receives Goods

### **With Pick & Pack**

Sales Order → Pick List → Packing Slip (optional) → Delivery Note → Delivery Trip

### **Without Sales Order**

Delivery Note → Dispatch
(Used for direct sales or sample items if allowed by company policy)

---

# **4. Key Features & Functions**

* Reduces stock from the warehouse.
* Supports batch and serial number tracking.
* Allows partial delivery of Sales Orders.
* Auto-fetches items from Sales Orders.
* Supports packaging, picking, and logistics operations.
* Tracks delivery status (Pending, Partially Delivered, Completed).
* Allows attaching delivery documents (LR copy, photos, POD).
* Can be used to trigger Delivery Trips.

---

# **5. Delivery Note Form – Detailed Fields**

---

## **5.1 Basic Information**

| Field                             | Description                                      |
| --------------------------------- | ------------------------------------------------ |
| **Customer / Receiver**           | The party receiving the goods.                   |
| **Delivery Note Date**            | Date of dispatch.                                |
| **Dispatch Location / Warehouse** | Warehouse from which goods are shipped.          |
| **Delivery To**                   | Delivery address or project site.                |
| **Sales Order**                   | If linked, items and quantities auto-fetch.      |
| **Transporter / Vehicle Info**    | Optional logistics details for tracking.         |
| **Remarks**                       | Additional notes about dispatch or instructions. |

---

## **5.2 Items Table (Delivered Items)**

Each row represents an item being delivered.

| Field            | Description                            |
| ---------------- | -------------------------------------- |
| **Item Code**    | The delivered item.                    |
| **Quantity**     | Quantity being dispatched.             |
| **UOM**          | Unit of measure.                       |
| **Warehouse**    | Warehouse from which items are issued. |
| **Batch No**     | Required for batch-controlled items.   |
| **Serial No**    | Mandatory for serialized items.        |
| **Packing Slip** | Reference to packaging (optional).     |
| **Description**  | Additional notes per item.             |

### Behavior:

* Items auto-fetch from Sales Order (if linked).
* Bundle items expand into their components.
* Batch/Serial must be selected before submit.

---

## **5.3 Delivery Status Fields**

| Field                            | Description                                                         |
| -------------------------------- | ------------------------------------------------------------------- |
| **Delivered Qty vs Ordered Qty** | Tracks partial, pending, or full delivery.                          |
| **Percentage Delivered**         | Shows fulfillment progress.                                         |
| **Is Returned?**                 | Indicates if this Delivery Note is a return (Return Delivery Note). |

---

## **5.4 Logistics & Transport Fields (Optional)**

| Field                      | Description                              |
| -------------------------- | ---------------------------------------- |
| **Driver**                 | Driver assigned to the delivery.         |
| **Vehicle No**             | Vehicle used for shipment.               |
| **LR No / Tracking ID**    | Consignment or logistic tracking number. |
| **Delivery Trip**          | Link to delivery trip record.            |
| **Expected Delivery Date** | Estimated delivery schedule.             |

These fields help coordinate logistics and route planning.

---

# **6. Behavior in Stock Operations**

### **6.1 Stock Deduction**

Upon submission:

* Stock is reduced from the warehouse for each item.
* Serial/Batch tracking ensures accuracy.
* Inventory reports immediately reflect updated quantities.

### **6.2 Multiple Deliveries Allowed**

If a Sales Order is partially delivered:

* System tracks pending quantities.
* Additional Delivery Notes can be created.

### **6.3 Handling of Product Bundles**

If a bundle item is selected:

* System automatically expands items inside the bundle.
* Only the component items affect stock.

### **6.4 Delivery Returns**

A **Return Delivery Note** is used to return delivered items back into stock.

Examples:

* Customer rejects goods.
* Wrong items delivered.
* Products returned due to quality issues.

---

# **7. Validations & Rules**

| Validation                                                | Purpose                             |
| --------------------------------------------------------- | ----------------------------------- |
| Cannot deliver more than ordered (if restriction enabled) | Prevents over delivery.             |
| Serial numbers must match quantity                        | Ensures proper serialized tracking. |
| Batch selection required for batch items                  | Ensures traceability.               |
| Adequate stock must exist in warehouse                    | Prevents negative stock.            |
| Address must be selected (if mandatory)                   | Ensures correct dispatch.           |
| Cannot edit submitted Delivery Notes                      | Ensures audit integrity.            |

---

# **8. Delivery Note Status Flow**

| Status                  | Description                                           |
| ----------------------- | ----------------------------------------------------- |
| **Draft**               | Not yet submitted.                                    |
| **Submitted**           | Goods are considered delivered.                       |
| **Partially Delivered** | Only some items delivered against linked Sales Order. |
| **Completed**           | All items delivered.                                  |
| **Returned**            | Delivery reversed using Return Delivery Note.         |
| **Cancelled**           | Delivery voided; stock movement reversed.             |

---

# **9. Integration with Other Modules**

*(No accounting connections included)*

| Module                                   | Integration Behavior                                 |
| ---------------------------------------- | ---------------------------------------------------- |
| **Sales Order**                          | Auto-fetches items and tracks delivery status.       |
| **Pick List**                            | Helps select correct items/locations for delivery.   |
| **Packing Slip**                         | Organizes packed items before dispatch.              |
| **Delivery Trip**                        | Tracks route, vehicle, and driver activity.          |
| **Quality Module**                       | May require QC signoff before dispatch (if enabled). |
| **Material Request (Internal Delivery)** | Supports internal item movement.                     |

---

# **10. Example Scenarios**

### 📌 **Scenario 1 – Partial Delivery**

Customer orders 100 units.
1st Delivery Note → 60 units
2nd Delivery Note → 40 units
System shows delivery progress at each step.

---

### 📌 **Scenario 2 – Delivery with Serial Numbers**

Laptop delivery → user selects serial numbers for each laptop.

---

### 📌 **Scenario 3 – Bundle Delivery**

"Home Starter Kit" → expands into 5 component items → only components deducted.

---

### 📌 **Scenario 4 – Delivery Return**

Customer rejects goods → Return Delivery Note created → stock returned to warehouse.

---

# **11. Summary**

A Delivery Note is essential for:

* Recording outbound stock movement
* Reducing inventory accurately
* Tracking delivery progress
* Supporting pick, pack, dispatch, and logistics workflows
* Maintaining proper batch/serial tracking
* Managing sales fulfillment

It is the central document for all shipping and dispatch operations.

---
