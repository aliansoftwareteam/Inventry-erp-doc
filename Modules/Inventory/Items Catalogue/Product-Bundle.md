# 📘 **Product Bundle – Detailed Documentation**

A **Product Bundle** is a packaged product that consists of multiple individual items sold together as one unit. The bundle itself does **not maintain stock**; instead, stock is tracked for each of its component items.

This feature is ideal for **kits, combo packs, promotional bundles, assembled sets**, or **service packages** where no manufacturing process is required.

---

# **1. Purpose of Product Bundle**

A Product Bundle allows organizations to:

* Sell multiple items together as a single product.
* Define kits or combo offers without creating a manufactured item.
* Automatically load component items during sales transactions.
* Simplify order entry and packing for combo products.
* Maintain inventory accuracy by deducting component stock.

---

# **2. How Product Bundles Work**

A Product Bundle consists of:

### **1. Parent Item (Bundle Item)**

* Represents the bundle as a product.
* Should be a **non-stock item**.
* Appears in sales transactions as the main product.

### **2. Component Items**

* Actual stock items used to build the bundle.
* Quantities are reduced from inventory during Delivery Note or Stock Entry.

### **Behavior:**

* When a bundle is added to a Sales Order:

  * The system automatically expands the bundle into its component items.
  * The parent item serves as the description/representation of the package.
  * The child items handle all stock movement.

---

# **3. Use Cases of Product Bundles**

Product Bundles are commonly used for:

### ✔ **Combo Packs**

Example: Keyboard + Mouse + Mousepad

### ✔ **Gift Sets**

Example: Chocolate Box + Greeting Card + Candle

### ✔ **Sales Promotional Packs**

Example: Buy 2 Get 1 Free

### ✔ **Tool Kits**

Example: Wrench + Screwdriver Set + Hammer

### ✔ **Service Packages**

Example: Installation + Training + Maintenance

---

# **4. Product Bundle Structure**

A bundle is defined with:

* **Parent Item** → bundle
* **Child Items** → list of items included in the bundle

Example:

| Bundle Item        | Component Item | Qty |
| ------------------ | -------------- | --- |
| OFFICE-STARTER-KIT | Office Chair   | 1   |
|                    | Office Table   | 1   |
|                    | Table Lamp     | 1   |

No stock is maintained for the bundle. Stock is maintained for the components.

---

# **5. Product Bundle Master – Detailed Fields**

Below is a detailed explanation of fields available in the Product Bundle configuration.

---

## **5.1 Basic Information**

| Field             | Description                                        |
| ----------------- | -------------------------------------------------- |
| **Parent Item**   | The bundle item. Must be a non-stock item.         |
| **Enable Bundle** | Activates the bundle behavior for the parent item. |
| **Description**   | Optional description of the bundle for clarity.    |

---

## **5.2 Component Items Table**

Each row defines one component of the bundle.

| Field           | Description                                       |
| --------------- | ------------------------------------------------- |
| **Item Code**   | Component item included in the bundle.            |
| **Quantity**    | Required quantity of the component.               |
| **UOM**         | Unit of Measure of the item (pcs, box, kg, etc.). |
| **Description** | Additional details for component items.           |

**Notes:**

* Components must be valid items.
* Quantities must be positive.
* Bundles cannot contain other bundles (no nesting).

---

# **6. Behavior in Sales & Stock Transactions**

### **6.1 Sales Order**

* User selects the bundle item.
* The system automatically loads the component items underneath it.
* Bundle item acts as a summary line; component items act as individual product lines.

### **6.2 Delivery Note**

* Only **component items** are delivered.
* Bundle item does not affect stock.
* Stock levels of the components decrease based on quantities defined in the bundle.

### **6.3 Sales Invoice**

Two display options typically exist:

1. Show **bundle item only**
2. Show **bundle item + component items**

(Depends on company preference—no accounting impact included.)

### **6.4 Stock Ledger**

* Only component items create stock movement entries.
* Bundle item does not appear in stock valuation or movement reports.

---

# **7. Product Bundle vs. Bill of Materials (BOM)**

| Feature      | Product Bundle                 | Bill of Materials (BOM)             |
| ------------ | ------------------------------ | ----------------------------------- |
| Purpose      | Sell items together            | Manufacture items                   |
| Stock Update | Only child items are delivered | Raw materials consumed, FG produced |
| Parent Item  | Non-stock                      | Stock item                          |
| Suitable For | Sales kits, combos             | Production assembly                 |

**Important:** Bundles do **not** trigger manufacturing. They do not create finished goods.

---

# **8. Validations & Rules**

| Rule                                           | Why It Exists                           |
| ---------------------------------------------- | --------------------------------------- |
| Parent item must be non-stock                  | Prevents incorrect stock tracking.      |
| Bundle cannot include another bundle           | Avoids circular dependencies.           |
| Component quantity must be positive            | Prevents invalid stock deduction.       |
| Components must be defined before using bundle | Ensures accuracy in sales and delivery. |
| UOM must match valid item UOM                  | Ensures correct stock handling.         |

---

# **9. Integration with Other Modules**

| Module                 | Behavior                                                                             |
| ---------------------- | ------------------------------------------------------------------------------------ |
| **Selling**            | Expands bundle items into components during order entry.                             |
| **Stock**              | Deducts component inventory at time of delivery.                                     |
| **Manufacturing**      | Not used for production; bundles are sales-only structures.                          |

(As per your rule, **no accounting module connections are mentioned**.)

---

# **10. Example Scenario**

### Bundle: **SMART-HOME-STARTER**

| Component Item | Qty |
| -------------- | --- |
| Smart Bulb     | 2   |
| Smart Plug     | 1   |
| Motion Sensor  | 1   |
| Wi-Fi Hub      | 1   |

Customer buys the bundle →
System expands into components →
Delivery Note ships the 5 items →
Component stock is deducted →
Bundle itself has no stock movement.

---