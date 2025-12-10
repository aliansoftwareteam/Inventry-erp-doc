# 📘 **UOM Conversion Factor – Detailed Documentation**

The **UOM Conversion Factor** defines the relationship between two different Units of Measure for the same item.
It allows items to be purchased, stocked, sold, or consumed in different units while maintaining consistency in stock updates and inventory control.

UOM Conversion Factors ensure accuracy in quantity calculations across **purchasing, manufacturing, sales, and stock transactions**.

---

# **1. Purpose of UOM Conversion Factor**

UOM Conversion Factors are used to:

* Convert quantities automatically between purchase UOM and stock UOM.
* Enable multi-UOM handling (box → pcs, kg → grams).
* Ensure accurate stock updates regardless of the transaction UOM.
* Maintain operational flexibility in item handling.
* Prevent manual conversion errors.
* Support packaging UOMs (carton, bundle, roll, etc.).

Conversion factors ensure that **different units of the same item are always aligned with the system’s Stock UOM**.

---

# **2. When UOM Conversions Are Used**

Conversions are required when:

### ✔ Items are purchased in bulk units

Example: 1 box = 12 bottles

### ✔ Manufacturing requires different UOM

Example: Material stored in kg but consumed in grams

### ✔ Sales and stock use different UOMs

Example: Stock UOM = pcs, Sales UOM = carton (24 pcs)

### ✔ Repack operations require UOM transformation

Example: 1 drum = 200 liters

### ✔ Warehouse teams handle mixed UOMs

Example: Count in pallets, but stock in pieces

---

# **3. Structure of UOM Conversion Factor**

A conversion factor links:

```
1 Unit of UOM A = X Units of UOM B
```

For example:

```
1 Box = 12 Pieces
1 Kg = 1000 Grams
1 Roll = 50 Meters
```

The system uses this factor to convert quantities during every transaction.

---

# **4. UOM Conversion Factor Master – Detailed Fields**

---

## **4.1 Basic Details**

| Field                 | Description                                                  |
| --------------------- | ------------------------------------------------------------ |
| **Item Code**         | Item for which conversion applies.                           |
| **UOM**               | Alternate UOM (purchase, sales, or additional).              |
| **Conversion Factor** | The multiplier relation between Stock UOM and alternate UOM. |

---

## **4.2 Example Breakdown**

If Stock UOM = pcs
Alternate UOM = box
Conversion factor = 12
Meaning:

```
1 box = 12 pcs
```

If Stock UOM = kg
Alternate UOM = gram
Conversion factor = 1000
Meaning:

```
1 kg = 1000 g
```

---

## **4.3 Additional Fields**

| Field                        | Description                                                |
| ---------------------------- | ---------------------------------------------------------- |
| **Description**              | Notes about packaging, measurement, or supplier specifics. |
| **Is Default Purchase UOM?** | Marks this UOM as the standard for purchase (optional).    |
| **Is Default Sales UOM?**    | Marks this UOM as the standard for sales (optional).       |

---

# **5. Behavior in Operations**

The conversion factor affects all stock-driven workflows:

---

## **5.1 Purchase Transactions**

Example:
PO: 10 boxes
1 box = 12 pcs
System automatically converts at receipt:

```
10 boxes → 120 pcs added to stock
```

---

## **5.2 Sales Transactions**

Sales in cartons while stock is maintained in pcs:

```
1 carton = 24 pcs  
5 cartons sold → 120 pcs deducted
```

---

## **5.3 Manufacturing Consumption**

Work Order needs 150g
Stock UOM = kg
Conversion factor = 1 kg = 1000g
System calculates:

```
150g → 0.15 kg consumed
```

---

## **5.4 Repack Operations**

Example:
1 drum = 200 liters
System automatically distributes quantities during repack transactions.

---

## **5.5 Warehouse Operations**

Pick List and Delivery Note show correct UOM conversions for:

* Picking
* Packing
* Dispatch
* Transfers

---

# **6. Validation Rules**

| Rule                                           | Purpose                                              |
| ---------------------------------------------- | ---------------------------------------------------- |
| Conversion factor must be positive             | Avoids invalid transformations.                      |
| UOM category must match logical dimensionality | Prevents illogical conversions (e.g., kg → pcs).     |
| One item cannot have duplicate UOM lines       | Prevents confusion.                                  |
| Decimal conversion factors allowed             | Useful for fractional units (e.g., 1 coil = 1.5 kg). |

---

# **7. Integration with Other Modules**

| Module                   | Integration Behavior                              |
| ------------------------ | ------------------------------------------------- |
| **Item Master**          | Maintains primary (Stock UOM) and alternate UOMs. |
| **Purchase Order**       | Uses conversion during receipt.                   |
| **Purchase Receipt**     | Converts alternate UOM to Stock UOM.              |
| **Delivery Note**        | Converts Sales UOM to Stock UOM.                  |
| **Stock Entry / Repack** | Uses conversion for multi-UOM operations.         |
| **Work Order / BOM**     | Consumes materials with correct UOM conversions.  |
| **Pick List**            | Reflects converted quantity while picking.        |

---

# **8. Example Conversion Factor Scenarios**

---

### 📌 **Scenario 1 – Packaging Conversion**

Item: Soft Drink
Stock UOM = bottle
Sales UOM = carton
Conversion: 1 carton = 12 bottles
Sales Order for 5 cartons → Delivery picks 60 bottles.

---

### 📌 **Scenario 2 – Weight Conversion**

Item: Chemical Powder
Stock UOM = kg
Alternate UOM = gram
Conversion: 1 kg = 1000 g
Work Order requires 250g → System consumes 0.25 kg.

---

### 📌 **Scenario 3 – Supplier-Based Purchase UOM**

Supplier sells cables in rolls.
Stock UOM = meter
Purchase UOM = roll
Conversion: 1 roll = 50 meters
10 rolls received → 500 meters added to stock.

---

### 📌 **Scenario 4 – Retail Packaging**

Item: Rice
Stock UOM = kg
Sales UOM = bag
Conversion: 1 bag = 5 kg
Selling 6 bags → reduces 30 kg from stock.

---

# **9. Summary**

UOM Conversion Factors enable:

* Accurate and automatic quantity conversions
* Smooth purchasing and selling in alternate units
* Proper manufacturing and consumption planning
* Error-free stock movements
* Consistent UOM usage across all modules

They are essential for businesses dealing with multiple packaging units, bulk purchases, and flexible sales units.

---