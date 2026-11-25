# Mì Cay Seoul — Odoo ERP Implementation Project

An Odoo 17 Community ERP project for restaurant operations, focusing on business process analysis, point-of-sale operations, inventory and material management, payment workflow integration, and Power BI reporting.

## 1. Project Overview

This project explores how an ERP system can improve operational visibility and reduce manual work in restaurant management.

The project is based on the business case of Mì Cay Seoul, with a focus on the Nguyễn Gia Trí branch in Ho Chi Minh City. The analysis identifies operational challenges involving inventory tracking, ingredient consumption, stock discrepancies, and the use of business data for management reporting.

The proposed solution uses Odoo ERP and custom add-ons to connect restaurant operations with inventory management and business intelligence reporting.

**Project type:** ERP implementation and business process improvement  
**ERP platform:** Odoo 17 Community  
**Deployment environment:** Docker and PostgreSQL  
**Business domain:** Food & Beverage (F&B)  
**Focus areas:** Business Analysis, ERP Functional Implementation, Inventory Management, POS, and Business Intelligence

## 2. Business Problem

The initial business analysis identified several operational challenges:

- Inventory and ingredient consumption require additional manual tracking.
- Actual stock quantities may differ from theoretical consumption.
- Stocktaking and loss tracking can be time-consuming.
- Sales and inventory information need to be connected more effectively.
- Operational data can be further utilized for management reporting and decision-making.

The project analyzes the current **AS-IS** processes and proposes **TO-BE** workflows supported by Odoo ERP.

## 3. Business Analysis and Process Design

The project covers business analysis activities such as:

- Understanding the restaurant's operational context and business requirements.
- Analyzing existing sales, purchasing, inventory, stocktaking, and payment workflows.
- Identifying operational pain points and improvement opportunities.
- Modeling current and proposed business processes using BPMN.
- Mapping business requirements to Odoo modules and custom functionality.
- Considering user roles, operational controls, and reporting needs.

### Key Business Processes

1. **Sales and POS:** Record restaurant orders and sales transactions.
2. **Purchasing and Receiving:** Manage incoming ingredients and inventory receipts.
3. **Inventory Management:** Track stock quantities and inventory movements.
4. **Ingredient Consumption:** Use product recipes and Bills of Materials (BOM) as a basis for material consumption management.
5. **Stocktaking and Loss Tracking:** Compare recorded stock with actual quantities and investigate discrepancies.
6. **Payment Workflow:** Explore electronic payment integration and transaction status handling.
7. **Business Reporting:** Use operational data to support management analysis through Power BI.

## 4. Custom Odoo Add-ons

The project contains four custom add-ons:

### 4.1 Smart Material Management — `smart_material`

Focuses on ingredient-level inventory management and material consumption tracking.

The module is intended to support workflows such as:

- Tracking material consumption associated with restaurant operations.
- Recording material usage history.
- Recording stock discrepancies and material losses.
- Supporting low-stock monitoring and replenishment decisions.

### 4.2 POS Custom Receipt — `pos_receipt_custom`

Customizes the Point of Sale receipt presentation to better fit the restaurant's operational needs.

### 4.3 POS Payment Gateway — `pos_payment_gateway`

Provides a custom module for the electronic payment workflow.

The module is associated with the project's SePay/VietQR payment-integration scope. The exact transaction, callback, and payment-confirmation behavior should be verified against the implementation and test results before production use.

### 4.4 Smart BI Dashboard — `smart_bi_dashboard`

Adds a Power BI dashboard entry point within Odoo to make business reporting accessible from the ERP interface.

The embedded report requires the appropriate Power BI access permissions. Report refresh behavior depends on the Power BI dataset and its configured data connection.

## 5. Technology Stack

| Area | Technology |
|---|---|
| ERP platform | Odoo 17 Community |
| Backend customization | Python |
| ERP views and interfaces | XML, Odoo views and client assets |
| Database | PostgreSQL |
| Local deployment | Docker / Docker Compose |
| Business intelligence | Microsoft Power BI |
| Business process modeling | BPMN |
| Analysis and design | Business requirements, AS-IS / TO-BE workflows |

## 6. High-Level Solution Architecture

The project follows this conceptual architecture:

```text
Restaurant Operations
        |
        v
Odoo 17 Community
  |        |         |
  |        |         +--> Custom POS Receipt
  |        +------------> Smart Material Management
  +---------------------> Payment Workflow Module
        |
        v
   PostgreSQL
        |
        v
  Power BI Reporting
        |
        v
  Management Insights

Smart BI Dashboard
provides an entry point to the report within Odoo.
```

The actual data flow and refresh mechanism depend on the deployed configuration and the implementation of each integration.

## 7. Local Development Environment

The development environment uses Docker to run Odoo and PostgreSQL locally on Windows.

### Prerequisites

- Docker Desktop
- Docker Compose
- Odoo 17 Community image or compatible local deployment
- PostgreSQL configured for the Odoo instance
- The four custom add-ons included in this repository

### Setup Overview

1. Clone or download the repository.
2. Review the Docker Compose configuration and environment variables.
3. Place the custom add-ons in the directory mounted to Odoo's extra-addons path.
4. Configure database connection details and required credentials locally.
5. Start the services with Docker Compose.
6. Open Odoo and update the Apps list.
7. Install or upgrade the custom add-ons as required.
8. Verify the workflows using test data before using the system for any real business operation.

Example command:

```bash
docker compose up -d
```

The exact configuration may need to be adapted to your local Docker setup. Do not commit passwords, API keys, payment credentials, database dumps, or private configuration files.

## 8. Repository Structure

The intended repository structure is:

```text
micay-seoul-odoo-erp/
├── addons/
│   ├── smart_material/
│   ├── pos_receipt_custom/
│   ├── pos_payment_gateway/
│   └── smart_bi_dashboard/
├── docs/
│   ├── business-analysis/
│   ├── business-process/
│   ├── technical-design/
│   ├── testing/
│   └── power-bi/
├── screenshots/
├── .gitignore
├── docker-compose.yml
└── README.md
```

Adjust this structure to match the actual files in the repository. Only include directories and documents that are present.

## 9. Testing and Validation

Testing should cover both business workflows and technical behavior.

Suggested validation scenarios include:

- Creating and confirming a POS order.
- Verifying expected inventory movements.
- Checking material consumption records.
- Recording and reviewing stock discrepancies.
- Checking the behavior of low-stock notifications, where implemented.
- Verifying payment status transitions and callback handling, where implemented.
- Opening the Power BI report from Odoo with an authorized account.
- Restarting the Docker services and checking system availability.

Test results, screenshots, and known limitations should be documented separately. Features that have not been tested should not be described as production-ready.

## 10. Project Scope and Limitations

This is a learning and portfolio project based on a restaurant ERP use case.

- The business workflows and requirements are based on the project report and may not represent every process used by the actual business.
- Custom functionality and integration behavior depend on the current code and local configuration.
- Electronic payment integration requires appropriate credentials, secure callback validation, and end-to-end testing before production use.
- Power BI embedding requires appropriate report permissions and a correctly configured data connection.
- Business data should be anonymized or replaced with sample data before public sharing.
- Accounting, HR, and other future extensions should be documented separately unless they have been implemented and tested.

## 11. Skills Demonstrated

- Business requirements analysis
- AS-IS / TO-BE process analysis
- BPMN business process modeling
- ERP module mapping and functional configuration
- Odoo custom module organization
- Inventory and material management concepts
- POS workflow analysis
- Integration planning and validation
- PostgreSQL data awareness
- Power BI reporting integration
- Functional testing and documentation
- Docker-based development environment

## 12. Project Documentation

The `docs/` directory can contain selected project artifacts, such as:

- Business requirements and scope
- AS-IS and TO-BE BPMN diagrams
- Functional requirements and process descriptions
- Solution architecture and module mapping
- Test scenarios and results
- Power BI dashboard screenshots and data-flow documentation

The original academic report can be shared separately after reviewing personal information, team member details, and any content that should not be publicly distributed.

## 13. Disclaimer

This repository is intended for educational and portfolio purposes. It is not an official Mì Cay Seoul production system. Any use with real business data or payment transactions requires additional security, integration, and operational validation.
