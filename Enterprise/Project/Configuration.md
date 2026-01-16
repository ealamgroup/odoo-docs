# Odoo Project App – Complete User Guide 

This guide explains how to use the Odoo Project App in a simple and practical way. It shows how you can manage projects, track costs, handle labor, connect sales and purchases, invoice customers, and finally calculate profit.

---

## 1. Project Starts from Sales

Everything begins with a **Sales Quotation**.

1. Abdul Rehman creates a **Quotation** in Odoo.
2. The quotation is sent to the customer.
3. When the customer approves it:
   - The quotation becomes a **Sales Order**.
   - If the product is project-based, Odoo can:
     - Automatically create a **Project**
     - Create initial **Tasks**
     - Link the Project with the Sales Order

Now this Sales Order number becomes your **Project Reference**.  
Example:  
`SO/0256 – Office Renovation Project`

This reference is your project’s identity card 🪪.

---

## 2. Project Structure

Inside the Project App, you can manage:

- Tasks
- Task stages (To Do, In Progress, Done)
- Milestones
- Deadlines
- Dependencies
- Planned hours vs actual hours

Each project acts like a digital file that holds:
- Work progress
- Costs
- Purchases
- Labor
- Profitability

---

## 3. Purchase Orders with Project Reference

All expenses must be linked to the project.  
This is done using **Purchase Orders (POs)**.

Each PO must contain:
- The same **Project Reference**
- Or a custom **Project field** 

This way, every cost is tied to the correct project.

---

## 4. Purchase Orders for Items (Material Cost)

For materials like:
- Cement
- Steel
- Fabric
- Tools
- Equipment

Process:
1. Create a Purchase Order
2. Select Vendor
3. Add Products
4. In Reference or Project field:
   - Enter: `SO/0256`
   - Or select the Project from dropdown

Now these materials belong to that project.

---

## 5. Purchase Orders for Workers / Daily Labor

This is where many people get confused, but it’s actually simple.

### Option A – Treat Labor as a Service Product 

One-time setup:
Create a product:
- Name: `Daily Labor`
- Type: Service
- Unit: Day or Hour
- Purchase price: Worker’s daily rate

Usage:
1. Create Purchase Order
2. Vendor: Labor contractor or worker
3. Product: `Daily Labor`
4. Quantity: Number of days
5. Unit price: Daily rate
6. Project reference: `SO/0256`

Example:
5 Workers × 10 Days × 2,000 = 100,000

Now labor cost is cleanly recorded.

---

### Option B – Individual Workers as Vendors

If each worker is paid separately:
- Create each worker as a Vendor
- Use the same “Labor Service” product
- Create PO per worker
- Link to the same Project

---

## 6. Why Linking to Project is Powerful

When:
- Sales Order
- Purchase Orders
- Labor
- Materials

All are linked to the same project:

You get:
- Clean reporting
- Accurate costing
- No confusion
- No manual searching

Your project becomes a financial storybook:
Every rupee has a reason and a place.

---

## 7. Reporting & Profit Calculation

Your report logic becomes very simple:

1. Get Customer Sales Order Amount  
2. Get all Purchase Orders where:
   - Reference = Project Code

Then:
Profit = Sales Order Amount
– Total Purchase Orders Amount

Example:
Sales Order = 500,000
Materials PO = 280,000
Labor PO = 120,000
Total Cost = 400,000
Profit = 100,000

Clear. Honest. Reliable.

---

## 8. Timesheets (Optional but Powerful)

If your team logs time:
- Each employee fills timesheet
- Time is linked to tasks
- Tasks are linked to projects
- Odoo calculates:
  - Labor cost
  - Project utilization
  - Profit impact

This is for companies that want **professional-grade tracking**.

---

## 9. Reference Field vs Custom Project Field

| Method | Pros | Cons |
|------|------|------|
Reference Field | Quick | Risk of typing mistakes |
Custom Project Field | Accurate, dropdown based | Needs small customization |

Recommendation: Always use a **Project field**.

---

## 10. Final Flow in Simple Words

1. Quote → Sales Order  
2. Sales Order → Project  
3. Project → Reference Code  
4. All Purchases & Labor → Linked to Project  
5. Project → Cost Tracking  
6. Cost vs Sales → Profit  

Your ERP becomes a living business map 🗺.

---

## Final Thought

The Project App is not just a task manager.  
It is a **financial control system**, a **planning tool**, and a **profit calculator** rolled into one.

When used properly:
- No cost is hidden
- No profit is guessed
- Everything is visible
- Everything is connected

