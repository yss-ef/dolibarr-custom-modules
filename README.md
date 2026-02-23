# ⚙️ Custom Dolibarr ERP Modules | HTBS Africa

> **Professional Internship Project** | **Company:** HTBS Africa
> A collection of custom, purpose-built modules designed to extend the core functionalities of the **Dolibarr ERP/CRM** system. These plugins focus on streamlining financial operations, accounting workflows, and field intervention reporting.

## 📑 Table of Contents

* [Project Overview](https://www.google.com/search?q=%23-project-overview)
* [Included Modules](https://www.google.com/search?q=%23-included-modules)
* [Installation Guide](https://www.google.com/search?q=%23-installation-guide)
* [System Requirements](https://www.google.com/search?q=%23-system-requirements)

## 📋 Project Overview

This repository houses four distinct modules developed during a professional internship at **HTBS Africa**. They were engineered to address specific business logic requirements that are not covered by Dolibarr's native feature set, particularly in the areas of treasury management and custom taxation.

## 🧩 Included Modules

| Module Name | Directory | Description |
| --- | --- | --- |
| **💰 Treasury Management** | `Module-1_Tresorerie` | A comprehensive module built to track, manage, and forecast company cash flows and treasury operations. |
| **📊 Accounting Allocation** | `Module-2_Ventile` | An extension designed to automate and streamline accounting breakdown/allocation (ventilation) processes. |
| **🧾 Custom Taxation** | `Module-3-CustomTax` | Enables the creation, application, and management of highly customized, non-native tax rules and rates within the ERP. |
| **📋 Intervention Report** | `modele-pv-intervention` | A custom document template (ODT/PDF) structured to automatically generate formal field intervention reports (Procès-Verbaux). |

## 🚀 Installation Guide

To install and activate these modules in your local Dolibarr environment (assuming a standard LAMP/LEMP stack on **Fedora 43** or similar Linux distributions):

**1. Locate your Dolibarr `custom` directory**
Typically, this is located within your web server's document root:

```bash
cd /var/www/html/dolibarr/htdocs/custom/

```

**2. Clone the repository**

```bash
sudo git clone https://github.com/yss-ef/[REPOSITORY_NAME].git .

```

**3. Set appropriate permissions**
Ensure the web server user (e.g., `apache` or `nginx`) has the correct read/write permissions:

```bash
sudo chown -R apache:apache /var/www/html/dolibarr/htdocs/custom/
sudo chmod -R 755 /var/www/html/dolibarr/htdocs/custom/

```

**4. Activate the modules**

1. Log in to your Dolibarr application as an Administrator.
2. Navigate to **Setup** (Configuration) > **Modules/Applications**.
3. Locate the new modules under their respective tabs and click the status toggle to **Enable** them.

## 💻 System Requirements

* **Dolibarr ERP/CRM:** Version 14.0 or higher (verify specific module compatibility if running older versions).
* **PHP:** 7.4+ (PHP 8.x recommended).
* **Database:** MariaDB / MySQL.

---

*Authored by Youssef Fellah.*

*Developed as part of an internship - HTBS Afriqua*




