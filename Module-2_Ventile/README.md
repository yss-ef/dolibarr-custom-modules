# 💱 Dolibarr Splitpayment Module

> **Dolibarr ERP/CRM Extension | Version 14.0+**
> This module allows users to split a single invoice payment into two distinct transactions routed to two different bank accounts. It is specifically engineered to handle international payments where a portion of the funds is retained in a foreign currency, and the remainder is converted into the local currency.

## 📑 Table of Contents

* [Technical Context](https://www.google.com/search?q=%23-technical-context)
* [Core Features](https://www.google.com/search?q=%23-core-features)
* [Database Requirements](https://www.google.com/search?q=%23-database-requirements)
* [Installation Guide](https://www.google.com/search?q=%23-installation-guide)
* [Usage Workflow](https://www.google.com/search?q=%23-usage-workflow)

## ⚙️ Technical Context

This module was explicitly developed to ensure compatibility with Dolibarr 14.0+. Due to specific API limitations within this version regarding multi-currency payment splitting, the module utilizes direct, optimized SQL queries. This architectural choice guarantees the strict robustness and consistency of your accounting data.

## ✨ Core Features

* **Quick Action Button:** Injects a "Split Payment" (`Ventiler un règlement`) action button directly onto the validated invoice card.
* **Dual Routing:** Seamlessly divides a total payment amount into two separate deposits targeting distinct internal bank accounts.
* **Multi-Currency Management:** Handles the conversion logic when transferring a portion of a foreign currency payment into Dolibarr's default local currency.
* **Manual Exchange Rates:** Allows the operator to input the exact real-world exchange rate applied by the bank during the transaction, ensuring precise accounting.
* **Real-Time Calculation:** The user interface automatically computes and previews the converted amounts dynamically as data is entered.
* **Strict Data Integrity:** The module automatically orchestrates the creation of all required underlying records (payments, invoice linkages, extrafields, and bank ledger entries) to maintain absolute database consistency.

## 🗄️ Database Requirements

Upon activation, the module relies on an extrafield named `batch_ref` linked to payments to logically group the two split transactions.

> **⚠️ CRITICAL: Manual Schema Update Required**
> This module requires the existence of a specific table for payment extrafields. You must ensure `llx_payment_extrafields` exists in your MySQL/MariaDB database before use.

| Column Name | Data Type | Description |
| --- | --- | --- |
| `fk_object` | `INT` | Foreign key mapping to the payment ID (`llx_paiement.rowid`). |
| `batch_ref` | `VARCHAR` | Storage field for the unique split batch reference string. |

## 🚀 Installation Guide

To install this module on a standard **Fedora 43** web server environment:

**1. Deploy the Module**
Extract the repository contents and move the `splitpayment` directory into your Dolibarr custom modules folder.

```bash
sudo cp -r splitpayment /var/www/html/dolibarr/htdocs/custom/
sudo chown -R apache:apache /var/www/html/dolibarr/htdocs/custom/splitpayment

```

**2. Verify Prerequisites**
Ensure the following native Dolibarr modules are active:

* Banks and Cash (`banque`)
* Invoices (`facture`)

**3. Activate the Module**

1. Log into Dolibarr with Administrator privileges.
2. Navigate to **Home > Setup > Modules/Applications**.
3. Locate **"Splitpayment"** in the list and click the activation toggle.

## 📖 Usage Workflow

1. Open a validated, unpaid (or partially paid) customer invoice.
2. Navigate to the "Add payment" section and click the new **"Split Payment"** button.
3. On the split configuration form, enter the **Total received amount** in the invoice's original currency.
4. For **Split 1**, input the amount to be deposited without conversion and select the target bank account (typically your foreign currency account).
5. For **Split 2**, input the remaining amount to be converted, apply the exact bank exchange rate, and select the target local bank account. The converted total will calculate automatically.
6. Click **"Save payment"**.
7. The system will generate two distinct payment records, route them to their respective ledgers, and redirect you to the updated invoice.
