# 📄 Dolibarr Custom Intervention Report (PV) Template

> **Dolibarr ERP/CRM Extension**
> An advanced PDF document template engineered to generate bespoke Field Service Reports (*Procès-Verbaux d'Intervention*). This module replaces standard generic templates with a professional design, integrating smart features to automate data entry and dynamically adapt to specific business requirements.

## 📑 Table of Contents

* [Core Features](https://www.google.com/search?q=%23-core-features)
* [Mandatory Configuration (Extrafields)](https://www.google.com/search?q=%23%EF%B8%8F-mandatory-configuration-extrafields)
* [Installation Guide](https://www.google.com/search?q=%23-installation-guide)
* [Activation & Setup](https://www.google.com/search?q=%23-activation--setup)
* [Usage Workflow](https://www.google.com/search?q=%23-usage-workflow)

## ✨ Core Features

* **Professional Layout:** Upgrades the default Dolibarr PDF output to a clean, corporate-ready document structure.
* **Dynamic Data Injection:** Automatically maps and displays custom intervention metadata directly onto the final PDF.
* **Automated Time Tracking:** Intelligently calculates and displays precise start times, end times, and overall durations based on the individual tasks logged within the intervention card.
* **Contextual Adaptation:** Bypasses the limitations of generic documents by tailoring the output strictly to field service operations.

## ⚙️ Mandatory Configuration (Extrafields)

> **⚠️ CRITICAL:** For the PHP template to fetch and render the data correctly, you must manually create specific custom attributes (Extrafields) in Dolibarr. This is a one-time setup.

1. Navigate to **Home > Setup > Modules/Applications**.
2. Locate the **Interventions** module and click its setup icon (⚙️).
3. Go to the **Complementary attributes (Interventions)** tab.
4. Click **New attribute** and create the following six fields *exactly* as listed below:

| Field Label (Example) | Attribute Code | Data Type |
| --- | --- | --- |
| Intervention Type | `typeintervention` | String (1 line) |
| Technician / Assignee | `intervenant` | String (1 line) |
| Subject | `objet` | String (1 line) |
| Location | `lieu` | String (1 line) |
| Contract Number | `numeromarche` | String (1 line) |
| Quarter | `trimestre` | String (1 line) |

## 🚀 Installation Guide

Unlike standard modules that go into the `custom` folder, PDF models must be placed directly into the core document directories. To install this on your **Fedora 43** environment:

**1. Locate the downloaded file**
Ensure you have the `pdf_perso.modules.php` file ready.

**2. Copy to the core directory**
Execute the following command, adjusting the path to match your local Dolibarr web root:

```bash
sudo cp pdf_perso.modules.php /var/www/html/dolibarr/htdocs/core/modules/fichinter/doc/

```

**3. Set Permissions**

```bash
sudo chown apache:apache /var/www/html/dolibarr/htdocs/core/modules/fichinter/doc/pdf_perso.modules.php
sudo chmod 644 /var/www/html/dolibarr/htdocs/core/modules/fichinter/doc/pdf_perso.modules.php

```

## 🔌 Activation & Setup

1. Return to the **Interventions** module setup page (Home > Setup > Modules/Applications > Interventions ⚙️).
2. Scroll down to the **Interventions cards document models** section.
3. The new template (e.g., "PV Intervention Final") will now appear in the list.
4. Toggle the switch to **Enable** it.
5. *(Optional)* Click the star icon to set it as the default generation model for all future interventions.

## 📖 Usage Workflow

With the template installed and extrafields configured:

1. Create a new **Intervention Card** or modify an existing one.
2. Fill out the newly created custom fields (Type, Location, Contract, etc.).
3. Scroll down to the task lines. Add your tasks, ensuring you specify a **date**, **time**, and **duration** for each.
4. In the document generation section, select your custom template from the dropdown menu.
5. Click **Generate**. The final PDF will compile all metadata and automatically calculate the chronological execution of your tasks.
