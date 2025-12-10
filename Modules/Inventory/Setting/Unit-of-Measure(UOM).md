# 📘 **Unit of Measure (UOM) – Detailed Documentation**

A **Unit of Measure (UOM)** defines how the quantity of an item is counted, purchased, stocked, manufactured, or sold.
UOM ensures **consistency, accuracy, and clarity** across all stock and operational transactions such as Purchase Orders, Stock Entries, Delivery Notes, and Manufacturing processes.

It is a foundational master for all item-related operations.

---

# **1. Purpose of Unit of Measure**

The Unit of Measure system is used to:

* Standardize how items are measured throughout the system.
* Allow items to be purchased, stocked, and sold in different units.
* Prevent quantity ambiguity across warehouses and departments.
* Maintain precise conversion rules for multi-UOM transactions.
* Enable operational validation to prevent incorrect quantity entries.

A strong UOM structure ensures **accuracy in stock management** and **operational efficiency**.

---

# **2. Types of UOM**

UOMs can be classified based on their use:

### ✔ **Stock UOM**

The base unit in which inventory is maintained.
Example: pcs, kg, liter, meter.

### ✔ **Purchase UOM**

The unit in which items are purchased.
Example: box, bag, roll.

### ✔ **Sales UOM**

The unit used for selling items.
Example: carton, bundle.

### ✔ **Manufacturing / Conversion UOM**

Units used during production transformations.
Example: converting kg → grams, rolls → meters.

### ✔ **Alternative UOM**

Additional units defined using conversion factors.
Example: 1 box = 12 bottles.

---

# **3. UOM Master – Detailed Fields**

---

## **3.1 Basic Details**

| Field                      | Description                                                  |
| -------------------------- | ------------------------------------------------------------ |
| **UOM Name**               | Name of the unit (kg, pcs, box, carton).                     |
| **UOM Category**           | Category such as Weight, Length, Volume, Units, Time.        |
| **Must be Whole Number?**  | Restricts decimals (e.g., pcs cannot be 1.5; kg can be 1.5). |
| **Description (Optional)** | Additional details about the UOM.                            |

---

## **3.2 Advanced Behavioral Settings**

| Setting                 | Description                                              |
| ----------------------- | -------------------------------------------------------- |
| **Is Stock UOM**        | Marks this UOM as eligible for item stock.               |
| **Decimal Precision**   | Controls number of allowed decimal places.               |
| **Conversion Required** | Indicates if this UOM needs conversion to/from base UOM. |

---

# **4. How UOM Works in Transactions**

UOM affects all major operational processes:

---

## **4.1 Purchase Transactions**

Example:
Item stock UOM = pcs
PO UOM = box
Conversion: 1 box = 24 pcs
System auto-converts during receipt.

---

## **4.2 Sales Transactions**

Sales may use different UOMs (e.g., carton) while stock updates in base UOM.

---

## **4.3 Stock Movements**

Stock Entry movements respect UOM conversions during:

* Transfer
* Issue
* Repack
* Manufacturing

---

## **4.4 Manufacturing**

Raw materials may be required in grams, but stocked in kg.
UOM conversion ensures accurate consumption.

---

## **4.5 Internal Requests**

Material Request quantities follow the standard UOM rules.

---

# **5. Importance of UOM Categories**

UOM categories help prevent incorrect comparisons such as:

* kg vs liter
* meter vs box
* piece vs kg

Only UOMs within the **same category** can be converted.

Examples:

| Category | UOMs          |
| -------- | ------------- |
| Weight   | kg, gram, ton |
| Length   | meter, cm, mm |
| Volume   | liter, ml     |
| Units    | pcs, box, bag |

---

# **6. UOM Validation Rules**

| Rule                                            | Purpose                              |
| ----------------------------------------------- | ------------------------------------ |
| UOM must be defined before assigning to an item | Prevents invalid UOM entries.        |
| Decimal restriction prevents fractional units   | Ensures realistic quantity handling. |
| Conversion factor required for multi-UOM        | Prevents wrong stock movement.       |
| Category mismatch is not allowed                | Avoids illogical conversions.        |

---

# **7. Integration with Other Modules**

| Module                | Integration Behavior                                              |
| --------------------- | ----------------------------------------------------------------- |
| **Item Master**       | Each item has a Stock UOM; other UOMs are allowed via conversion. |
| **Purchase Order**    | Uses purchase UOM; converts on receipt.                           |
| **Purchase Receipt**  | Converts received quantity into stock UOM.                        |
| **Delivery Note**     | Converts dispatched quantity appropriately.                       |
| **Stock Entry**       | All transformations respect conversion factors.                   |
| **Bill of Materials** | Raw materials follow defined UOMs.                                |
| **Work Order**        | Ensures correct UOM for material consumption.                     |

---

# **8. Example Scenarios**

---

### 📌 **Scenario 1 – Purchase in Box, Stock in Pieces**

Stock UOM = pcs
Purchase UOM = box
Conversion = 1 box = 20 pcs
Purchase Receipt of 10 boxes → stock increases by 200 pcs.

---

### 📌 **Scenario 2 – Chemicals in Kg but Required in Grams**

Stock UOM = kg
Work Order requires 150 g
System converts automatically: 0.15 kg consumed.

---

### 📌 **Scenario 3 – Retail Packaging**

Stock UOM = kg
Sales UOM = packet
1 packet = 0.25 kg
Delivery Note for 8 packets → reduces 2 kg from stock.

---

# **9. Summary**

Unit of Measure ensures:

* Consistent quantity handling
* Accurate stock transactions
* Flexible purchase & sales operations
* Proper manufacturing and raw material consumption
* Realistic and error-free inventory control

It is a core master record that influences every stock and material movement process.

---