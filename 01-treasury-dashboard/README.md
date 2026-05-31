# Dolibarr treasury dashboard module

The treasury dashboard module for Dolibarr ERP/CRM provides a comprehensive
view of monthly cash flows and an annual synthesis of financial activities. It
enables managers to anticipate cash movements, track overdue payments, and
analyze overall financial health.

## Core features

- **Monthly summary board:** Displays a unified overview of realized and
  forecasted cash flows for the current month, including:
  - Total inflows inclusive of tax.
  - VAT collected on inflows.
  - Supplier outflows.
  - Special charges and expenses.
  - Estimated VAT disbursements based on debits.
  - Net monthly synthesis.
- **Interactive annual view:** A summary table presenting indicators month-by-
  month for a full calendar year, including annual totals and a dynamic year
  selector.
- **Overdue tracking:** Dedicated tables to identify client and supplier
  invoices that have passed their due dates.
- **Granular data lists:** Separates forecasted transactions from realized
  activities for precise financial tracking.
- **Visual analytics:** Integrates charts within the monthly view to
  visualize cash flow synthesis and weekly commercial activity trends.

## System prerequisites

Ensure the Dolibarr environment meets the following requirements:

- **Core system:** Dolibarr ERP/CRM version 7.0 or higher.
- **Required modules:** The following native modules must be active:
  - Invoices (`facture`)
  - Banks and Cash (`banque`)
  - Expense Reports (`ndfp`)
  - Taxes, VAT, and Social Dividends (`tax`)

## Installation guide

Follow these steps to install and configure the module on a local server.

### 1. Deploy the source code

Copy the `tresoreriemensuelle` directory into the Dolibarr `custom` folder:

```bash
sudo cp -r tresoreriemensuelle /var/www/html/dolibarr/htdocs/custom/
sudo chown -R apache:apache /var/www/html/dolibarr/htdocs/custom/tresoreriemensuelle
```

### 2. Activate the module

1. Log into the Dolibarr instance as an administrator.
2. Navigate to **Home > Setup > Modules/Applications**.
3. Locate **Tableau de Bord Trésorerie** (Treasury Dashboard) in the list and
   enable it.

### 3. Configure user permissions

1. Navigate to **Home > Users & Groups**.
2. Select the relevant user or group.
3. Under the **Permissions** tab, grant the **View the treasury dashboard**
   permission.

## User guide

After activation and permission assignment, a new **Treasury** (*Trésorerie*)
entry appears in the top-level navigation bar.

- **Treasury > Monthly view:** Access detailed dashboards and visual charts
  for the current month.
- **Treasury > Annual view:** Access the financial summary broken down by
  month. Use the input field at the top to toggle between fiscal years.

## Credits

Developed by Youssef Fellah during a professional internship at HTBS Africa.
