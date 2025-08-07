# 📦 Part 3: Product Setup & Warehouse Configuration

Now let’s set up our products — both physical goods and services — and assign correct accounts to track revenue and expenses.

We’ll also configure warehouses and internal stock locations for proper inventory management.

---

## 🔹 Step 1: Open Products

**Path:**  
`Sales → Products → Products → Create`

We’ll start with a **storable product** — which Odoo will track in inventory.

---

## 🔹 Step 2: Create a Storable Product (e.g., Wooden Table)

| Field                  | Value                      |
|------------------------|----------------------------|
| **Product Name**       | Wooden Table               |
| **Product Type**       | Storable Product           |
| **Sales Price**        | PKR 15,000                 |
| **Cost**               | PKR 10,000                 |

**Inventory Tab:**
- Route: ✅ Buy  
- ✅ Receive in Stock

**Accounting Tab:**

| Account Type   | Account Code & Name         |
|----------------|-----------------------------|
| Income Account | `60000 – Revenue`           |
| Expense Account| `70000 – Cost of Sales`     |

> (Product Category can assign accounts automatically, but we’ll set them manually for now)

Click **Save** to create the product.

---

## 🔹 Step 3: Create a Service Product (e.g., Interior Design)

Repeat the process for a service:

| Field                  | Value                          |
|------------------------|--------------------------------|
| **Product Name**       | Interior Design Service        |
| **Product Type**       | Service                        |
| **Sales Price**        | PKR 50,000                     |

**Accounting Tab:**

| Account Type   | Account Code & Name                |
|----------------|------------------------------------|
| Income Account | `60000 – Revenue`                  |
| Expense Account| _(Optional)_ `71000 – Subcontracting Expense` |

Click **Save**.

✅ Now we have both a tracked item (Wooden Table) and a non-stocked service (Interior Design).

---

## 🏬 Step 4: Enable Multi-Warehouse & Storage Locations

**Path:**  
`Inventory → Configuration → Settings`

Enable:

- ☑️ Multi-Warehouses  
- ☑️ Storage Locations

Click **Save** to activate warehouse features.

---

## 🏢 Step 5: Create a Warehouse

**Path:**  
`Inventory → Configuration → Warehouses → Create`

| Field             | Value               |
|------------------|---------------------|
| Warehouse Name   | Karachi Warehouse   |
| Short Name       | KHI                 |
| Location Address | _(Optional)_        |

Click **Save**.

---

## 📍 Step 6: Explore Internal Stock Locations

Once a warehouse is created, Odoo auto-generates internal stock zones.

**Path:**  
`Inventory → Configuration → Locations`

Apply filter:  

You’ll see:

| Location       | Description                              |
|----------------|-------------------------------------------|
| KHI/Input      | Incoming goods (pending inspection)       |
| KHI/Stock      | Available inventory (ready for sale/use)  |
| KHI/Output     | Goods ready to deliver to customers       |

✅ These locations allow precise control over product movement within the warehouse.

---

## ✅ Summary

- Products (both goods & services) are set up with correct pricing and accounts  
- Multi-warehouse mode is enabled  
- One warehouse with standard internal zones (Input, Stock, Output) is created  
- Ready for purchase, delivery, and inventory tracking
