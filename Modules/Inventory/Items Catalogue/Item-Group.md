# 📘 **Item Group – Detailed Documentation**

The **Item Group** is a classification tool used in the Stock (Inventory) module to organize Items into logical categories. Item Groups support **reporting, pricing, analytics, permissions, and configuration inheritance**.

An efficient Item Group structure improves searchability, reporting, costing analysis, and integration with various modules such as Buying, Selling, Manufacturing.

---

# **1. Purpose of Item Group**

Item Group is used to:

* Categorize items into meaningful groups (e.g., Raw Materials, Finished Goods, Components, Services).
* Structure items hierarchically for better reporting and management.
* Apply default settings—such as accounts and tax templates—at the group level.
* Enable better analytics in Stock, Sales, and Purchase reports.
* Improve navigation and organization of large item databases.
* Control permissions for users based on groups.
* Support pricing and discount structures.

---

# **2. Item Group Structure**

Item Groups support a **tree (hierarchical)** structure.

Example:

```
Items
 ├── Raw Materials
 │     ├── Steel
 │     ├── Plastic
 │     └── Chemicals
 ├── Finished Goods
 ├── Spare Parts
 └── Services
```

This hierarchy helps:

* Roll-up reporting (e.g., total value for Raw Materials)
* Inherited properties for child groups
* Logical classification for large inventories

---

# **3. Key Features of Item Group**

| Feature                             | Description                                                                    |
| ----------------------------------- | ------------------------------------------------------------------------------ |
| **Hierarchical Categorization**     | Organize groups under parent–child structure for clarity and reporting.        |
| **Automatic Assignment**            | Items inherit many properties when linked to an Item Group.                    |
| **Filtering & Search Optimization** | Helps locate items faster in transactions and reports.                         |
| **Reporting Segmentation**          | Enables group-based reporting like Stock Valuation, Sales, and Purchases.      |

---

# **4. Item Group Master – Detailed Fields Explanation**

Below are the fields typically available in the Item Group master.

| Field                 | Description                                                                 |
| --------------------- | --------------------------------------------------------------------------- |
| **Item Group Name**   | Name of the group (e.g., Raw Material, Consumables).                        |
| **Parent Item Group** | Select another Item Group to create a hierarchical structure.               |
| **Is Group**          | If enabled, this group can have subgroups. If disabled, it is a leaf group. |
| **Description**       | Additional information about the category, shown in reports/tooltips.       |

---