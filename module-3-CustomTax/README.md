# 🧾 Dolibarr CustomTax Module

> **Dolibarr ERP/CRM Extension**
> The **CustomTax** module provides ultimate flexibility in managing tax labels on financial documents. It allows users to dynamically customize the tax acronym (e.g., "TVA", "VAT", "GST", "Sales Tax") directly on a per-invoice basis. This is an essential tool for companies operating internationally that need to bypass Dolibarr's hardcoded tax labels.

## 📑 Table of Contents

* [Project Overview](https://www.google.com/search?q=%23-project-overview)
* [Installation Guide](https://www.google.com/search?q=%23-installation-guide)
* [Mandatory Configuration (Extrafields)](https://www.google.com/search?q=%23%EF%B8%8F-mandatory-configuration-extrafields)
* [Document Template Setup](https://www.google.com/search?q=%23-document-template-setup)
* [Usage Workflow](https://www.google.com/search?q=%23-usage-workflow)

## 📋 Project Overview

Natively, Dolibarr restricts invoices to a single, static tax label defined in the global dictionary. This module solves that limitation by injecting a custom attribute (Extrafield) into the invoice creation process. Combined with a customized ODT (OpenDocument Text) template, it maps the user's input to dynamically render the correct localized tax acronym on the final generated PDF/ODT.

## 🚀 Installation Guide

To install the module on your **Fedora 43** web server:

**1. Deploy the Module**
Copy the `customtax` directory into your Dolibarr custom modules folder:

```bash
sudo cp -r customtax /var/www/html/dolibarr/htdocs/custom/
sudo chown -R apache:apache /var/www/html/dolibarr/htdocs/custom/customtax

```

**2. Activate the Module**

1. Log into your Dolibarr instance with an Administrator account.
2. Navigate to **Home > Setup > Modules/Applications**.
3. Locate the **CustomTax** module in the list and click **Enable**.

## ⚙️ Mandatory Configuration (Extrafields)

> **⚠️ CRITICAL:** For the module to function, you must manually create the database attribute that will store the custom tax string. This is a one-time setup.

1. Navigate to **Home > Setup > Modules/Applications**.
2. Find the **Invoices and Credit Notes** module and click its setup icon (⚙️).
3. Go to the **Complementary attributes (invoices)** tab.
4. Click **New attribute** and fill out the form using the *exact* values below:

| Field | Required Value |
| --- | --- |
| **Label / Translation key** | `Tax Name` |
| **Attribute code** | `custom_tax_name` |
| **Type** | `String (1 line)` |
| **Default value** | `TVA` (or your most common tax) |
| **Visibility** | `1` |

5. Click **Save**.

## 📄 Document Template Setup

Once the attribute is created, you must upload the custom `.odt` document template that contains the logic to display the new tax name.

1. Remain in the **Invoices and Credit Notes** setup area (Home > Setup > Modules/Applications > Invoices ⚙️).
2. Navigate to the **Document models** tab.
3. Scroll down to the upload form for invoice models.
4. Click **Choose File** and select the `.odt` file provided with this module repository.
5. Click **Add model** to upload it to the server. The template will now be available in your document generation dropdowns.

## 📖 Usage Workflow

With the module installed, the extrafield configured, and the ODT template uploaded:

1. Create a new invoice or modify an existing one.
2. Locate the newly injected field labeled **Tax Name**.
3. Enter the required tax acronym for this specific client (e.g., "GST").
4. Scroll down to the document generation section.
5. From the "Model to use" dropdown, **select the newly uploaded ODT template**.
6. Click **Generate**. The final document will dynamically render the custom tax acronym you provided.
