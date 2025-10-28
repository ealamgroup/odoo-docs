
# Odoo 18 Community Edition – Access Groups and Permissions Guide

This document provides a **comprehensive, structured, and developer-friendly guide** to managing **Access Groups** and **Permissions** in Odoo 18 Community Edition.

---

## 🧩 Purpose of Access Groups in Odoo
Access groups in Odoo help users **focus on relevant tasks** by restricting visibility and protecting **sensitive business data** (e.g., contacts, sales, or accounting).

### Key Objectives
| Purpose | Explanation |
|----------|--------------|
| Focus | Users see only what’s relevant to their role. |
| Security | Prevent unauthorized access to confidential data. |
| Efficiency | Simplifies menus and interfaces for better workflow. |

---

## 🧠 Understanding Odoo Groups
Odoo uses **Groups** to define what users can view, create, write, or delete.

| Concept | Description |
|----------|-------------|
| **Group** | A set of permissions assigned to one or more users. |
| **Inheritance** | Groups can inherit rights from other groups (e.g., Administrator → User All Documents → User Owned Documents Only). |
| **Default Groups** | Internal User, Portal, Public. |
| **Usage** | Used for menus, fields, record rules, and access rights. |

### 🧩 Example Inheritance Chain
```
Administrator
 └── User: All Documents
      └── User: Own Documents Only
```

---

## 🧭 Limiting Access to an Application (Example: Contacts App)
Restrict access to the **Contacts app** by controlling **menu visibility** instead of changing record rules.

### Steps
1. Go to **Settings → Users & Companies → Groups → Create New Group**.  
   Example: `Technical / Contacts Access`  
2. Under **Menus**, add “Contacts” and remove “Internal User.”  
3. Assign this group only to users who should access Contacts.  
4. Test under a non-admin user account.  

### Example XML Snippet
```xml
<record id="group_contacts_restricted" model="res.groups">
    <field name="name">Technical / Contacts Access</field>
    <field name="category_id" ref="base.module_category_contacts"/>
</record>

<record id="menu_contacts_restricted" model="ir.ui.menu">
    <field name="groups_id" eval="[(6, 0, [ref('group_contacts_restricted')])]"/>
</record>
```

---

## 🔐 Limiting Visibility Within a Record (Example: Hidden Tab)
You can limit visibility of specific **tabs or fields** inside a model.

### Example: “Super Secret Info” Tab in Contacts
1. Create a new tab in **Odoo Studio** (e.g., “Super Secret Info”).  
2. Set **Group Visibility** to your custom group (e.g., `Technical / Contacts Access`).  
3. If your group lacks an external ID:
   - Export it from Odoo with the **External ID** field included.  
   - This forces Odoo to assign one.  
4. Apply this ID in Studio for conditional visibility.

### XML Example
```xml
<xpath expr="//page[@name='contact_information']" position="after">
    <page name="secret_tab" string="Super Secret Info" groups="your_module.group_contacts_restricted">
        <field name="secret_field"/>
    </page>
</xpath>
```

---

## ⚙️ Example Record Rules
| Rule Name | Model | Domain | Perms (Read/Create/Write/Delete) |
|------------|--------|--------|----------------------------------|
| Own Contacts Only | res.partner | [('user_id', '=', user.id)] | 1 / 1 / 1 / 0 |
| Read Only Employees | hr.employee | [] | 1 / 0 / 0 / 0 |

---

## 📁 Example Access Rights File (ir.model.access.csv)
| Model | Group | Perms | Example |
|--------|--------|--------|----------|
| `res.partner` | `group_contacts_restricted` | read,write,create | ✅ |
| `hr.employee` | `base.group_user` | read | ✅ |

Example CSV Row:
```csv
access_partner_restricted,res.partner,model_res_partner,group_contacts_restricted,1,1,1,0
```

---

## 🧱 Safety and Best Practices

| Tip | Description |
|-----|--------------|
| ✅ Modify Menus | Safest method to control app visibility. |
| ⚠️ Avoid Record Rules (Unless Needed) | Complex domains can cause permission errors. |
| 🧑‍💻 Always Test | Use a test user account to verify access levels. |
| 🔒 Backup First | Before editing access control or record rules. |
| 🧰 Developer Mode | Enable it to find technical names for menus and models. |

---

## 🧾 Quick Reference Summary

| Task | Path | Type | Example |
|------|------|------|----------|
| Create Group | Settings → Users & Companies → Groups | UI | Technical / Contacts Access |
| Add Menu Access | Settings → Technical → User Interface → Menus | UI/XML | Contacts Menu |
| Limit Tab | Odoo Studio | UI/XML | Super Secret Info |
| Export External ID | Settings → Technical → Export | UI | group_contacts_restricted |

---

### ✅ Final Note
Managing Access Groups properly ensures security, clarity, and performance in Odoo 18 Community Edition. Start simple—**limit menus first**, then move to **record and field-level control** only as needed.
