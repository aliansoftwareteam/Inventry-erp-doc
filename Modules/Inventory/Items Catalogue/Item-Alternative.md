# 📘 **Item Alternative – Detailed Documentation**

**Item Alternative** is a feature used to define substitute or interchangeable items that can be used when the primary item is unavailable or not preferred.
This ensures smooth operations in **purchase, sales, manufacturing, and stock transactions** by allowing flexibility in selecting replacement items.

Item Alternatives improve material planning, avoid delays, and support efficient decision-making when stock shortages occur.

---

# **1. Purpose of Item Alternative**

The Item Alternative feature is used to:

* Define substitute items for a primary item.
* Ensure continuity when the main item is out of stock.
* Suggest alternative items during sales or purchase order creation.
* Improve material planning for manufacturing or internal consumption.
* Support stock optimization by utilizing interchangeable items.
* Help warehouse and procurement teams identify possible replacement materials.

---

# **2. When Item Alternatives are Used**

Item Alternatives are beneficial for:

### ✔ Raw materials with similar specifications

Example: Two types of bolts with slightly different brands but same size.

### ✔ Consumables

Example: Paper A4 (Brand X) can be substituted with A4 (Brand Y).

### ✔ Packaging materials

Example: 500 ml bottle (Type A) can be substituted with 500 ml bottle (Type B).

### ✔ Common components in manufacturing

Example: Electrical connectors, cables, nuts, washers.

### ✔ Sales order replacements

Example: Customer-selected product out of stock → suggest compatible product.

---

# **3. Item Alternative Structure**

Item Alternative consists of:

* **Primary Item** – the main item.
* **Alternative Item(s)** – substitute items that can be used instead.
* **Similarity or Priority Factor** (optional) – indicates closeness or preference.

Example:

| Item                | Alternative                | Priority |
| ------------------- | -------------------------- | -------- |
| ITEM-STEEL-ROD-12MM | ITEM-STEEL-ROD-12MM-BRAND2 | 1        |
| ITEM-STEEL-ROD-12MM | ITEM-STEEL-ROD-12MM-BRAND3 | 2        |

Priority can be used to automate suggestions.

---

# **4. Item Alternative Master – Detailed Fields**

Below are the fields typically available in the Item Alternative configuration.

---

## **4.1 Basic Information**

| Field                     | Description                                                       |
| ------------------------- | ----------------------------------------------------------------- |
| **Item Code**             | The main (primary) item for which alternatives are being defined. |
| **Alternative Item Code** | The substitute item that can be used in place of the main item.   |
| **Description**           | Additional explanation about compatibility or usage.              |
| **Is Active**             | Enables or disables an alternative item without deleting it.      |

---

## **4.2 Priority or Similarity Index (If Supported)**

| Field                     | Description                                                                      |
| ------------------------- | -------------------------------------------------------------------------------- |
| **Priority**              | Determines which alternative is preferred first. Lower number = higher priority. |
| **Similarity Percentage** | Indicates how similar the alternative is to the main item (optional).            |

This helps the system suggest the most suitable replacement automatically.

---

# **5. Behavior in Transactions**

### **5.1 Sales Orders**

* When the main item is out of stock, the system can:

  * Suggest an alternative item.
  * Allow user to replace it with a substitute item.

### **5.2 Purchase Orders**

* If a vendor cannot supply the original item, procurement can select an alternative.
* Alternatives appear in search results to simplify replacement.

### **5.3 Material Request / Manufacturing**

* During raw material planning:

  * The system may suggest alternative items if primary stock is insufficient.
  * Helps avoid production delays due to shortages.

### **5.4 Stock Issuance**

Store teams can quickly identify replacement items based on the predefined alternative list.

---

# **6. Scenarios Where Item Alternatives Improve Efficiency**

### 📌 **Scenario 1 – Out of Stock During Sales**

Item A is not available → system suggests Item B as an alternative.

### 📌 **Scenario 2 – Vendor Cannot Supply Material**

Procurement selects replacement item from the alternative list.

### 📌 **Scenario 3 – Manufacturing Shortage**

Production planner checks Item Alternatives to maintain workflow.

### 📌 **Scenario 4 – Warehouse Replacement**

For standard consumables, warehouse staff uses alternatives for internal requests.

---

# **7. Limitations / Rules**

| Rule                                                            | Purpose                                    |
| --------------------------------------------------------------- | ------------------------------------------ |
| UOM of alternative item should match the main item              | Ensures accurate consumption and planning. |
| Do not create circular alternatives (A → B → A)                 | Avoids confusion.                          |
| System will not automatically change items unless user confirms | Prevents accidental substitutions.         |
| Alternative item must be active                                 | Inactive items will not be suggested.      |

---

# **8. Example Setup**

### Primary Item:

**CEMENT-BAG-50KG**

### Alternatives:

| Alternative Item       | Priority | Note                           |
| ---------------------- | -------- | ------------------------------ |
| CEMENT-BAG-50KG-BRAND2 | 1        | Same strength, different brand |
| CEMENT-BAG-50KG-BRAND3 | 2        | Acceptable substitute          |

**Use Case:**
If BRAND1 is unavailable → BRAND2 is suggested automatically.

---
