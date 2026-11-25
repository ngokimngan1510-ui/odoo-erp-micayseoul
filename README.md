# odoo-erp-micayseoul
Odoo 17 Community ERP project for restaurant operations, featuring smart material management, POS receipt customization, SePay/VietQR payment integration, and embedded Power BI dashboards.
# Mì Cay Seoul — Odoo ERP Integration Project

## 1. Project Overview

This project explores the implementation and customization of **Odoo 17 Community** for restaurant operations at Mì Cay Seoul.

The system focuses on integrating point-of-sale operations, inventory and material management, payment processing, and business intelligence reporting into a unified ERP workflow.

The project follows a business-process-oriented approach: identifying operational needs, configuring Odoo, developing custom add-ons, and connecting operational data to management reports.

## 2. Business Context

Traditional restaurant operations may rely on separate POS software, spreadsheets, and manual inventory records. This can make it difficult to track ingredient consumption, reconcile inventory differences, monitor low-stock items, and analyze business performance.

This project explores how Odoo and custom integrations can support more consistent operational data and management visibility.

## 3. Key Features

### Smart Material Management
**Module:** `smart_material`

- Track ingredient consumption associated with POS orders.
- Use Bill of Materials (BOM) to define ingredient requirements.
- Maintain material consumption history.
- Record inventory checks and material losses.
- Provide low-stock alerts and replenishment support.

### POS Receipt Customization
**Module:** `pos_receipt_custom`

- Customize the Odoo POS receipt template.
- Extend the POS interface using Odoo frontend assets.

### Payment Integration
**Module:** `pos_payment_gateway`

- Integrate SePay and VietQR payment workflows.
- Generate QR payment information for transactions.
- Receive payment notifications through webhooks.
- Track payment transaction status and its relationship with POS orders.
- Support invoice email workflows where configured.

### Power BI Dashboard Integration
**Module:** `smart_bi_dashboard`

- Add a Power BI reporting menu to the Odoo interface.
- Embed a published Power BI report.
- Support access to management dashboards for sales, inventory, purchasing, and material consumption.

**Note:** Data freshness depends on the Power BI semantic model, data source connectivity, and refresh configuration. Embedding a report does not itself provide real-time data synchronization.

## 4. Technology Stack

- **ERP:** Odoo 17 Community
- **Backend:** Python
- **Database:** PostgreSQL
- **Frontend customization:** XML, JavaScript, OWL
- **Deployment environment:** Docker and Docker Compose
- **Business intelligence:** Microsoft Power BI
- **Payment integration:** SePay, VietQR, webhooks

## 5. Business Processes

The main operational flow covered by the project is:

1. Configure products, ingredients, and inventory data in Odoo.
2. Process customer orders through Point of Sale (POS).
3. Record ingredient consumption according to configured BOM rules.
4. Monitor inventory levels and inventory discrepancies.
5. Process supported QR payment workflows and receive transaction notifications.
6. Analyze operational data through Power BI reports.

The actual behavior of each workflow depends on the installed modules and system configuration.

## 6. Repository Structure

```text
micay-seoul-odoo-erp/
├── addons/
│   ├── smart_material/
│   ├── pos_receipt_custom/
│   ├── pos_payment_gateway/
│   └── smart_bi_dashboard/
├── docs/
│   ├── business-process/
│   ├── data-model/
│   ├── power-bi/
│   └── testing/
├── screenshots/
├── .gitignore
├── docker-compose.yml
└── README.md
```

This is the proposed repository structure. Adjust folder names to match the actual files included in the repository.

## 7. Setup

Prerequisites:

- Docker Desktop
- Docker Compose
- Odoo 17 Community
- PostgreSQL

Deployment instructions, environment variables, module installation steps, and Power BI connection configuration will be documented after the repository structure and configuration files are verified.

Do not commit passwords, API keys, webhook secrets, database dumps, or private business data.

## 8. Project Scope and Limitations

This repository documents a learning and portfolio project. Features should be considered implemented only when the corresponding code and workflows are available and tested.

Power BI refresh behavior depends on the configured data connection and refresh settings. Payment integrations require valid credentials and appropriate webhook configuration.

## 9. Screenshots and Demonstrations

Screenshots and demonstrations will be added to document:

- Odoo POS order processing
- Ingredient and inventory management
- Inventory loss records and low-stock alerts
- QR payment workflow
- Power BI dashboards embedded in Odoo

Use screenshots that do not expose credentials, customer information, or sensitive operational data.

## 10. Skills Demonstrated

- ERP process analysis and workflow mapping
- Odoo configuration and custom module development
- Inventory and POS process integration
- External payment service integration
- PostgreSQL data access and reporting
- Power BI dashboard integration
- Docker-based development and deployment
