# Dolibarr ERP Custom Modules

A collection of professional-grade extensions for the Dolibarr ERP/CRM ecosystem, developed to optimize financial workflows, accounting precision, and operational reporting. These modules were engineered to address complex business requirements during a professional internship at HTBS Africa.

## Project Overview

This repository contains four specialized modules designed to extend Dolibarr's core functionality. The focus of this project was to automate manual accounting tasks and provide real-time treasury insights that are not available in the native ERP distribution.

---

## Technical Stack

*   **Platform**: Dolibarr ERP/CRM (v14.0+)
*   **Language**: PHP 7.4+ / 8.x
*   **Database**: MySQL / MariaDB (Relational Modeling)
*   **Integration**: Hook & Trigger System, Module Descriptor (CRUD logic)
*   **Reporting**: ODT/PDF Template Engine

---

## Core Modules

### 1. Treasury Management (`Module-1_Tresorerie`)
*   **Function**: Advanced cash flow tracking and financial forecasting.
*   **Key Logic**: Implements real-time monitoring of bank accounts and expected payments to provide a consolidated view of company liquidity.

### 2. Accounting Allocation & Ventilation (`Module-2_Ventile`)
*   **Function**: Automation of complex accounting breakdowns.
*   **Key Logic**: Streamlines the process of "ventilation" (allocation) of accounting entries across multiple cost centers, reducing manual entry errors and ensuring audit compliance.

### 3. Custom Taxation Engine (`module-3-CustomTax`)
*   **Function**: Dynamic tax rule management.
*   **Key Logic**: Allows for the definition and application of customized tax rates and rules that fall outside standard national taxation tables, providing flexibility for specific international or regional trade requirements.

### 4. Intervention Report Model (`modele-pv`)
*   **Function**: Automated document generation for field services.
*   **Key Logic**: A structured report generation system that pulls real-time intervention data into formal Process-Verbal (PV) documents, ensuring professional and standardized reporting for clients.

---

## System Architecture

The modules are built following the standard Dolibarr development patterns:
*   **Module Descriptor**: Defines permissions, menus, and database tables.
*   **Business Logic**: Encapsulated in PHP classes for maintainability.
*   **User Interface**: Integrated seamlessly into the existing Dolibarr HUD (Heads-Up Display).

---

## Deployment & Installation

### Prerequisites
*   Functioning Dolibarr installation (LAMP/LEMP stack).
*   Administrative access to the ERP.

### Installation Steps
1.  **Navigate** to your Dolibarr `custom` directory:
    ```bash
    cd /path/to/dolibarr/htdocs/custom/
    ```
2.  **Clone** this repository:
    ```bash
    git clone git@github.com:yss-ef/dolibarr-custom-modules.git
    ```
3.  **Permissions**: Ensure the web server has appropriate read/write access to the cloned folders.
4.  **Activation**: Enable the modules via **Setup > Modules/Applications** in the Dolibarr admin panel.

Authored by Youssef Fellah.  
Developed during professional internship at HTBS Africa.
