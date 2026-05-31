# Dolibarr CustomTax module

The CustomTax module provides flexibility in managing tax labels on financial
documents. It allows users to dynamically customize the tax acronym, such as
TVA, VAT, GST, or Sales Tax, directly on a per-invoice basis. This tool is
essential for companies operating internationally that must bypass Dolibarr's
hardcoded tax labels.

## Project overview

Natively, Dolibarr restricts invoices to a single, static tax label defined in
the global dictionary. This module resolves this limitation by injecting a
custom attribute into the invoice creation process. Combined with a customized
OpenDocument Text (ODT) template, it maps user input to dynamically render the
correct localized tax acronym on the final generated document.

## Installation guide

Follow these steps to install the module on a web server.

### 1. Deploy the module

Copy the `customtax` directory into your Dolibarr custom modules folder:

```bash
sudo cp -r customtax /var/www/html/dolibarr/htdocs/custom/
sudo chown -R apache:apache /var/www/html/dolibarr/htdocs/custom/customtax
```

### 2. Activate the module

1. Log into the Dolibarr instance with an administrator account.
2. Navigate to **Home > Setup > Modules/Applications**.
3. Locate the **CustomTax** module in the list and click **Enable**.

## Mandatory configuration

For the module to function, you must manually create the database attribute
that stores the custom tax string. This is a one-time setup.

1. Navigate to **Home > Setup > Modules/Applications**.
2. Locate the **Invoices and Credit Notes** module and click its setup icon.
3. Select the **Complementary attributes (invoices)** tab.
4. Click **New attribute** and complete the form using the exact values
   below:

| Field | Required value |
| :--- | :--- |
| **Label / Translation key** | `Tax Name` |
| **Attribute code** | `custom_tax_name` |
| **Type** | `String (1 line)` |
| **Default value** | `TVA` |
| **Visibility** | `1` |

5. Click **Save**.

## Document template setup

After creating the attribute, upload the custom `.odt` document template that
contains the logic to display the new tax name.

1. Remain in the **Invoices and Credit Notes** setup area (**Home > Setup >
   Modules/Applications > Invoices**).
2. Select the **Document models** tab.
3. Scroll to the upload form for invoice models.
4. Click **Choose File** and select the `.odt` file provided with this module.
5. Click **Add model** to upload it to the server. The template is now
   available in the document generation dropdown menu.

## Usage workflow

1. Create a new invoice or modify an existing one.
2. Locate the field labeled **Tax Name**.
3. Enter the required tax acronym for the specific client, such as GST.
4. Scroll to the document generation section.
5. In the **Model to use** dropdown, select the newly uploaded ODT template.
6. Click **Generate**. The final document dynamically renders the custom tax
   acronym provided.

## Credits

Developed by Youssef Fellah during a professional internship at HTBS Africa.
