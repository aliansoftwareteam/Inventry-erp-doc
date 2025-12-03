# **📘 BOM Update Tool Documentation**

The **BOM Update Tool** is designed to simplify bulk maintenance of Bills of Materials (BOMs) inside your manufacturing system. With this tool, you can easily replace outdated BOMs, push new revisions, and update costing across all BOMs with one click. This ensures accuracy, reduces manual work, and keeps your production data consistent.

---

# **1. Getting Started**

The BOM Update Tool helps you quickly apply large-scale changes to your Bill of Materials across your manufacturing setup. It provides two primary functions:

* **Replace BOM** – Swap an existing BOM with a new one across all parent BOMs.
* **Update Cost** – Recalculate all BOM costs based on the latest material/item prices.

You should use this tool whenever you:

* Introduce a new BOM revision
* Replace a discontinued sub-assembly
* Update cost structures
* Want to ensure consistent data across all BOMs

### **Accessing the Tool**

Navigate to:
**Manufacturing → BOM Update Tool**

From here, you will see two main sections:

1. **Replace BOM**
2. **Update Cost**

---

# **2. Replace BOM**

The **Replace BOM** function allows you to globally replace one BOM with another across all higher-level BOMs in the system.

### **When to Use Replace BOM**

Use this feature when:

* A BOM revision changes (e.g., V1 → V2)
* A component BOM is discontinued
* You need to implement a new sub-assembly
* You want to update multiple BOM structures at once

### **Fields Explained**

| Field           | Description                                   |
| --------------- | --------------------------------------------- |
| **Current BOM** | The existing BOM you want to replace          |
| **New BOM**     | The updated BOM that will replace the old one |

### **How to Replace a BOM**

1. Enter/select the **Current BOM**
2. Enter/select the **New BOM**
3. Click **Replace**
4. The system scans all BOMs, replaces references, and saves updates
5. Review the changes using the **BOM Update Log**

### **What Happens After Replacement**

* The old BOM is replaced everywhere it appears as a component
* Parent BOMs and multi-level BOMs get updated
* A log entry is created for auditing
* No manual editing is required

### **Important Notes**

* Ensure the New BOM is valid and approved
* Replacement affects all BOMs in the system
* Action cannot be undone (but you can reverse by replacing again)

---

# **3. Update Cost**

The **Update Cost** feature automatically recalculates all BOM costs based on the latest item or component price.

### **When to Use Update Cost**

Run this whenever:

* Material prices change
* Supplier cost updates occur
* Components/sub-assemblies change
* You want accurate BOM costing for planning

### **How It Works**

When you click **Update latest price in all BOMs**, the system will:

1. Fetch the latest material prices
2. Recalculate cost totals for every BOM
3. Save updated costs
4. Record the action in the update log

### **Benefits**

* Always accurate manufacturing cost
* Better planning and forecasting
* No manual recalculations
* Reduces risk of using outdated pricing

---

# **4. BOM Update Log**

Click **View BOM Update Log** to see a complete history of:

* BOM replacements
* Cost update operations
* User performing the action
* Timestamps
* Total BOMs affected
* Success or error details

This helps with:

* Audit trails
* Troubleshooting
* Tracking revision history
* Cross-team communication

---

# **5. Summary**

The BOM Update Tool provides a fast, safe, and efficient way to:

* Replace outdated BOM structures
* Apply new BOM revisions globally
* Recalculate costs using the latest material prices
* Maintain consistent and accurate manufacturing data
* Reduce manual work for engineering and production teams

This tool is essential for any operation that regularly updates product structures, component prices, or BOM versions.
