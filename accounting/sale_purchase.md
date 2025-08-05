# 🔁 Part 5: Purchase & Sales Workflow (End-to-End Demo)

In this phase, we simulate a full business cycle:

- Vendor Purchase  
- Inventory Receipt  
- Vendor Bill & Payment  
- Customer Sale  
- Delivery  
- Customer Invoice & Payment  

Odoo handles inventory, accounting, and logistics in sync — all from one place.

---

## 🛒 Purchase Flow: From RFQ to Bank Payment

---

### 🔹 Step 1: Create a Request for Quotation (RFQ)

**Path:**  
`Purchases → Orders → Requests for Quotation → Create`

| Field              | Value                 |
|--------------------|-----------------------|
| **Vendor**         | Al-Furqan Traders     |
| **Product**        | Wooden Table          |
| **Quantity**       | 10                    |
| **Unit Price**     | 10,000 PKR            |
| **Subtotal**       | 100,000 PKR           |
| **Delivery Date**  | _(Set manually)_      |

Click **Confirm Order**.  
✅ RFQ is now a **Purchase Order** and a delivery (receipt) is automatically created.

---

### 🔹 Step 2: Receive the Goods

- Click the **Receipts** smart button on the PO.
- This opens the **Incoming Shipment**.
- Check quantities (should be 10).
- Click **Validate**.

✅ Inventory now includes 10 Wooden Tables under `KHI/Stock`.

---

### 🔹 Step 3: Create the Vendor Bill

- Back on the PO, click **Create Bill**.
- Odoo auto-fills the bill using PO details.
- Click **Confirm** to post the vendor bill.

✅ The bill is now in **Accounts Payable**.

---

### 🔹 Step 4: Register Payment to Vendor

- Click **Register Payment** on the vendor bill.

| Field              | Value                 |
|--------------------|-----------------------|
| **Amount**         | 100,000 PKR           |
| **Payment Journal**| Meezan Bank           |
| **Method**         | Manual / Bank Transfer|

Click **Validate**.

✅ The vendor bill is marked **Paid**, and bank transaction is recorded.  
📌 Journal entries for cash/bank and payable are created behind the scenes.

---

## 🛍️ Sales Flow: From Quotation to Customer Payment

---

### 🔹 Step 5: Create a Quotation

**Path:**  
`Sales → Orders → Quotations → Create`

| Field              | Value                 |
|--------------------|-----------------------|
| **Customer**       | Ali Enterprises       |
| **Product**        | Wooden Table          |
| **Quantity**       | 5                     |
| **Unit Price**     | 15,000 PKR            |
| **Subtotal**       | 75,000 PKR            |
| **Delivery Date**  | _(Optional)_          |

Click **Confirm**.  
✅ Quotation becomes a **Sales Order**. A delivery order is created automatically.

---

### 🔹 Step 6: Deliver the Product

- Click the **Delivery** smart button on the Sales Order.
- Odoo opens the warehouse transfer.
- Since stock is available, click **Validate** to ship.

✅ 5 Wooden Tables are removed from stock.

---

### 🔹 Step 7: Create a Customer Invoice

- Go back to the Sales Order → Click **Create Invoice**.
- Choose: `Regular Invoice` → Click **Create & View Invoice**.
- Review invoice, click **Confirm**.

✅ The invoice is now posted in **Accounts Receivable**.

---

### 🔹 Step 8: Register Customer Payment

- Click **Register Payment** on the invoice.

| Field              | Value                 |
|--------------------|-----------------------|
| **Amount**         | 75,000 PKR            |
| **Payment Journal**| UBL Bank              |
| **Method**         | Bank                  |

Click **Validate**.

✅ The invoice is marked **Paid**, and the payment appears in UBL Bank journal.  
📌 Odoo creates accounting entries: Debit Bank, Credit Receivable.

---

## ✅ Final Outcome

| Activity            | Result                                      |
|---------------------|---------------------------------------------|
| Purchase            | Inventory increased + Payable posted       |
| Vendor Payment      | Bank journal updated                       |
| Sales               | Inventory decreased + Revenue recorded      |
| Customer Payment    | Receivable cleared + Bank updated           |

Odoo has now fully linked:

- 📦 Stock Movements  
- 💵 Journal Entries  
- 📑 Invoices & Bills  
- 🧾 Real-time Accounting  

All seamlessly handled in a clean ERP flow.

