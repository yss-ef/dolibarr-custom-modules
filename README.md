# Dolibarr ERP custom modules

This repository contains professional-grade extensions for the Dolibarr ERP/CRM
ecosystem designed to optimize financial workflows, accounting precision, and
operational reporting. These modules address complex business requirements by
automating manual accounting tasks and providing real-time treasury insights
not available in the native ERP distribution.

## Project overview

The repository includes four specialized modules that extend Dolibarr core
functionality. These tools were engineered to streamline financial operations
and enhance data visibility within the ERP environment.

## Technical stack

- **Platform:** Dolibarr ERP/CRM (v14.0+)
- **Language:** PHP 7.4 or 8.x
- **Database:** MySQL or MariaDB (relational modeling)
- **Integration:** Hook and trigger system, module descriptor (CRUD logic)
- **Reporting:** ODT and PDF template engine

## Core modules

### 1. Treasury management

The treasury management module provides advanced cash flow tracking and
financial forecasting. It implements real-time monitoring of bank accounts and
expected payments to offer a consolidated view of company liquidity.

### 2. Payment split and ventilation

The payment split and ventilation module automates complex accounting
breakdowns and multi-currency splitting. It streamlines the allocation
(ventilation) of accounting entries across multiple cost centers and bank
accounts.

### 3. Custom taxation engine

The custom taxation engine enables dynamic tax rule management and acronym
customization. It allows users to define and apply customized tax rates and
labels, such as VAT, GST, or TVA, on a per-invoice basis.

### 4. Intervention report model

The intervention report model facilitates automated document generation for
field services. This structured report generation system pulls real-time
intervention data into formal process-verbal (PV) documents.

## System architecture

The modules follow standard Dolibarr development patterns to ensure stability
and maintainability.

- **Module descriptor:** Defines permissions, menus, and database tables.
- **Business logic:** Encapsulated in PHP classes for maintainability.
- **User interface:** Integrated seamlessly into the existing Dolibarr HUD.

## Deployment and installation

### Prerequisites

- A functioning Dolibarr installation (LAMP or LEMP stack).
- Administrative access to the ERP instance.

### Installation steps

1. Navigate to the Dolibarr `custom` directory:
   ```bash
   cd /path/to/dolibarr/htdocs/custom/
   ```
2. Clone the repository:
   ```bash
   git clone git@github.com:yss-ef/dolibarr-custom-modules.git
   ```
3. Permissions: Ensure the web server has appropriate read and write access to
   the cloned folders.
4. Activation: Enable the modules through the **Setup > Modules/Applications**
   menu in the Dolibarr admin panel.

## Credits

Developed by Youssef Fellah during a professional internship at HTBS Africa.
