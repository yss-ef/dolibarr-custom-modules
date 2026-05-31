# Dolibarr splitpayment module

The splitpayment module for Dolibarr 14.0+ allows users to divide a single
invoice payment into two distinct transactions routed to different bank
accounts. It is engineered to handle international payments where a portion of
funds is retained in a foreign currency while the remainder is converted to
local currency.

## Technical context

This module is developed specifically for compatibility with Dolibarr 14.0+. To
address API limitations in this version regarding multi-currency payment
splitting, the module utilizes direct, optimized SQL queries. This architecture
ensures the robustness and consistency of accounting data.

## Core features

- **Quick action button:** Injects a **Split Payment** (*Ventiler un
  règlement*) button directly onto the validated invoice card.
- **Dual routing:** Divides a total payment amount into two separate deposits
  targeting distinct internal bank accounts.
- **Multi-currency management:** Handles conversion logic when transferring
  a portion of a foreign currency payment into the default local currency.
- **Manual exchange rates:** Allows operators to input exact real-world
  exchange rates applied by the bank, ensuring precise accounting.
- **Real-time calculation:** The interface automatically computes and previews
  converted amounts dynamically during data entry.
- **Data integrity:** Automatically orchestrates the creation of all required
  underlying records, including payments, invoice linkages, extrafields, and
  bank ledger entries.

## Database requirements

Upon activation, the module uses an extrafield named `batch_ref` linked to
payments to group the two split transactions.

### Manual schema update

This module requires a specific table for payment extrafields. Ensure the
`llx_payment_extrafields` table exists in the MySQL or MariaDB database before
use.

| Column name | Data type | Description |
| :--- | :--- | :--- |
| `fk_object` | `INT` | Foreign key mapping to the payment ID (`llx_paiement.rowid`). |
| `batch_ref` | `VARCHAR` | Storage for the unique split batch reference string. |

## Installation guide

Follow these steps to install the module on a standard web server environment.

### 1. Deploy the module

Extract the repository contents and move the `splitpayment` directory into the
Dolibarr custom modules folder:

```bash
sudo cp -r splitpayment /var/www/html/dolibarr/htdocs/custom/
sudo chown -R apache:apache /var/www/html/dolibarr/htdocs/custom/splitpayment
```

### 2. Verify prerequisites

Ensure the following native Dolibarr modules are active:
- Banks and Cash (`banque`)
- Invoices (`facture`)

### 3. Activate the module

1. Log into Dolibarr with administrator privileges.
2. Navigate to **Home > Setup > Modules/Applications**.
3. Locate **Splitpayment** in the list and enable it.

## Usage workflow

1. Open a validated, unpaid, or partially paid customer invoice.
2. Navigate to the **Add payment** section and click the **Split Payment**
   button.
3. In the split configuration form, enter the **Total received amount** in the
   invoice's original currency.
4. For **Split 1**, input the amount for deposit without conversion and select
   the target bank account.
5. For **Split 2**, input the remaining amount for conversion, apply the
   exact bank exchange rate, and select the target local bank account.
6. Click **Save payment**.
7. The system generates two distinct payment records, routes them to their
   respective ledgers, and redirects you to the updated invoice.

## Credits

Developed by Youssef Fellah during a professional internship at HTBS Africa.
