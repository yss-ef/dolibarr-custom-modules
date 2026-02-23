# 💰 Dolibarr Treasury Dashboard Module

> **Dolibarr ERP/CRM Extension**
> A comprehensive financial dashboard module designed to provide a clear, detailed view of monthly cash flows and an annual synthesis of financial activities. It empowers managers to anticipate cash movements, track overdue payments, and analyze overall financial health.

## 📑 Table of Contents

* [Core Features](https://www.google.com/search?q=%23-core-features)
* [System Prerequisites](https://www.google.com/search?q=%23%EF%B8%8F-system-prerequisites)
* [Installation Guide](https://www.google.com/search?q=%23-installation-guide)
* [User Guide](https://www.google.com/search?q=%23-user-guide)

## ✨ Core Features

* **Monthly Summary Board:** Displays a unified overview combining both **realized and forecasted** cash flows for the current month, including:
* Total inflows (inclusive of tax).
* VAT collected on inflows.
* Supplier outflows.
* Special charges and expenses.
* VAT to be disbursed (estimated based on debits).
* Net monthly synthesis.


* **Interactive Annual View:** A comprehensive summary table presenting key indicators month-by-month for a full calendar year, complete with annual totals. Includes a dynamic year selector.
* **Overdue Tracking:** Dedicated tables designed to instantly identify client and supplier invoices that have passed their due dates.
* **Granular Data Lists:** Strictly separates forecasted transactions (pending invoices, scheduled charges) from realized activities (paid invoices, settled charges) for precise financial tracking.
* **Visual Analytics:** Integrates two distinct charts within the monthly view to visualize cash flow synthesis and weekly commercial activity trends.

## ⚙️ System Prerequisites

Ensure your Dolibarr environment meets the following requirements before installation:

* **Core System:** Dolibarr ERP/CRM (Version 7.0 or higher).
* **Required Native Modules (Must be activated):**
* Invoices (`facture`)
* Banks and Cash (`banque`)
* Expense Reports (`ndfp`)
* Taxes, VAT, and Social Dividends (`tax`)



## 🚀 Installation Guide

To install and configure this module on your local server (e.g., **Fedora 43** with a standard web server stack):

**1. Deploy the Source Code**
Copy or clone the `tresoreriemensuelle` directory into your Dolibarr `custom` folder:

```bash
# Example path, adjust according to your specific web root
sudo cp -r tresoreriemensuelle /var/www/html/dolibarr/htdocs/custom/
sudo chown -R apache:apache /var/www/html/dolibarr/htdocs/custom/tresoreriemensuelle

```

**2. Activate the Module**

1. Log into your Dolibarr instance as an Administrator.
2. Navigate to **Home > Setup > Modules/Applications**.
3. Locate **"Tableau de Bord Trésorerie"** (Treasury Dashboard) in the list and click the toggle to enable it.

**3. Configure User Permissions**

1. Go to **Home > Users & Groups**.
2. Select the relevant user or group.
3. Under the **Permissions** tab, grant the right: **"View the treasury dashboard"**.

## 📖 User Guide

Once successfully activated and permissions are granted, a new top-level menu entry named **"Treasury"** (`Trésorerie`) will appear in your Dolibarr navigation bar.

* **Treasury > Monthly View:** Access the detailed dashboard and visual charts for the current month.
* **Treasury > Annual View:** Access the financial summary broken down by month. Use the input field at the top of the interface to toggle between different fiscal years.
