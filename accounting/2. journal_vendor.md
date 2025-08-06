# 🧾 Part 2: Journal Setup & Business Partner Configuration

Now that our **Chart of Accounts** is ready, it’s time to define how money flows through the system.

In Odoo, this is done through **Journals** — each journal represents a financial pathway such as a **bank**, **cash register**, or **sales pipeline**.

---

## 🔹 Step 1: Access Journal Configuration

**Path:**  
`Accounting → Configuration → Journals`

> You may already see default journals based on the fiscal localization selected earlier.

We'll now manually add **two bank journals** and review existing **Sales**, **Purchase**, and **Cash** journals.

---

## 🔹 Step 2: Create Meezan Bank Journal

Click **Create** and enter the following details:

| Field                   | Value                  |
|------------------------|------------------------|
| **Journal Name**       | Meezan Bank            |
| **Type**               | Bank                   |
| **Short Code**         | MEE                    |
| **Default Debit**      | `24100 – Meezan Bank`  |
| **Default Credit**     | `24100 – Meezan Bank`  |
| **Bank Account Number**| _(optional)_           |

Click **Save** to store the journal.

---

## 🔹 Step 3: Create UBL Bank Journal

Repeat the process for UBL Bank:

| Field                   | Value                 |
|------------------------|-----------------------|
| **Journal Name**       | UBL Bank              |
| **Type**               | Bank                  |
| **Short Code**         | UBL                   |
| **Default Debit**      | `24200 – UBL Bank`    |
| **Default Credit**     | `24200 – UBL Bank`    |

Click **Save**.

✅ You now have two fully functional bank journals ready for transactions.

---

## 🔹 Step 4: Review and Configure Other Journals

Let’s now verify default accounts on key journals:

### 🧾 Sales Journal

| Field                 | Account                |
|----------------------|------------------------|
| **Default Credit**   | `60000 – Revenue`      |
| **Default Debit**    | `22000 – Receivable`   |

### 📦 Purchase Journal

| Field                 | Account                |
|----------------------|------------------------|
| **Default Debit**    | `70000 – Cost of Sales`|
| **Default Credit**   | `42000 – Payable`      |

### 💵 Cash Journal

| Field                 | Account                |
|----------------------|------------------------|
| **Debit/Credit**     | `23000 – Cash in Hand` |

✅ With these journals in place, Odoo now knows **how to record** each financial transaction:
- Customer sales  
- Vendor bills  
- Cash and bank operations

---

# 🧍 Part 3: Vendor & Customer Setup

---

## 🔹 Step 5: Create a Vendor

**Path:**  
`Contacts → Create`

| Field                 | Sample Entry              |
|----------------------|---------------------------|
| **Name**             | Al-Furqan Traders         |
| **Is a Vendor**      | ☑️ Checked                |
| **City**             | Karachi / Lahore          |
| **Phone, Email**     | _(Optional)_              |
| **Tax ID**           | _(Optional)_              |
| **Website**          | _(Optional)_              |

**Accounting Tab:**
- You may manually assign a payable account
- But if company defaults are configured (like `42000 – Payable`), Odoo will link it automatically

Click **Save**.

---

## 🔹 Step 6: Create a Customer

Repeat the process:

| Field                 | Sample Entry              |
|----------------------|---------------------------|
| **Name**             | Ali Enterprises           |
| **Is a Customer**    | ☑️ Checked                |
| **City**             | Lahore / Islamabad        |
| **Phone, Email**     | _(Optional)_              |

**Accounting Tab:**
- `22000 – Account Receivable` is auto-set due to default company config

Click **Save**.

---

## ✅ Summary So Far

- 🏦 Journals are configured for bank, cash, sales, and purchases  
- 👥 Vendor and Customer contacts are created  
- 📒 Chart of Accounts is clean and fully linked

These contacts can now be used in:
- Purchase Orders  
- Bills  
- Quotations  
- Sales Invoices
