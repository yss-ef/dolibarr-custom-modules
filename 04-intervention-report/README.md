# Dolibarr custom intervention report template

This advanced PDF document template generates bespoke field service reports,
known as *Procès-Verbaux d'Intervention*. It replaces standard generic
templates with a professional design that integrates smart features to
automate data entry and dynamically adapt to specific business requirements.

## Core features

- **Professional layout:** Upgrades the default Dolibarr PDF output to a
  clean, corporate-ready document structure.
- **Dynamic data injection:** Automatically maps and displays custom
  intervention metadata directly onto the final PDF.
- **Automated time tracking:** Calculates and displays precise start times,
  end times, and overall durations based on individual tasks logged within the
  intervention card.
- **Contextual adaptation:** Tailors the output strictly to field service
  operations, bypassing the limitations of generic documents.

## Mandatory configuration

For the PHP template to fetch and render data correctly, you must manually
create specific custom attributes, or extrafields, in Dolibarr. This is a
one-time setup.

1. Navigate to **Home > Setup > Modules/Applications**.
2. Locate the **Interventions** module and click its setup icon.
3. Select the **Complementary attributes (Interventions)** tab.
4. Click **New attribute** and create the following six fields exactly as
   listed:

| Field label | Attribute code | Data type |
| :--- | :--- | :--- |
| Intervention type | `typeintervention` | String (1 line) |
| Technician / Assignee | `intervenant` | String (1 line) |
| Subject | `objet` | String (1 line) |
| Location | `lieu` | String (1 line) |
| Contract number | `numeromarche` | String (1 line) |
| Quarter | `trimestre` | String (1 line) |

## Installation guide

PDF models must be placed directly into core document directories rather than
the standard `custom` folder.

### 1. Locate the file

Ensure the `pdf_perso.modules.php` file is available for deployment.

### 2. Copy to the core directory

Execute the following command, adjusting the path to match your Dolibarr web
root:

```bash
sudo cp pdf_perso.modules.php /var/www/html/dolibarr/htdocs/core/modules/fichinter/doc/
```

### 3. Set permissions

```bash
sudo chown apache:apache /var/www/html/dolibarr/htdocs/core/modules/fichinter/doc/pdf_perso.modules.php
sudo chmod 644 /var/www/html/dolibarr/htdocs/core/modules/fichinter/doc/pdf_perso.modules.php
```

## Activation and setup

1. Return to the **Interventions** module setup page (**Home > Setup >
   Modules/Applications > Interventions**).
2. Scroll to the **Interventions cards document models** section.
3. The new template, such as **PV Intervention Final**, appears in the list.
4. Toggle the switch to enable it.
5. Optional: Click the star icon to set it as the default generation model.

## Usage workflow

1. Create a new intervention card or modify an existing one.
2. Complete the custom fields, such as type, location, and contract.
3. Add tasks in the task lines section, ensuring you specify a date, time, and
   duration for each.
4. In the document generation section, select the custom template from the
   dropdown menu.
5. Click **Generate**. The final PDF compiles all metadata and calculates the
   chronological execution of tasks automatically.

## Credits

Developed by Youssef Fellah during a professional internship at HTBS Africa.
