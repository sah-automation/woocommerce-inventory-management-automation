# WooCommerce Inventory Management Automation

An end-to-end automation solution built with **n8n** to streamline inventory management between **WooCommerce** and **Google Sheets**.

![Status](https://img.shields.io/badge/Status-Production-brightgreen)
![Orchestrator](https://img.shields.io/badge/Orchestrator-n8n-orange)
![Database](https://img.shields.io/badge/Database-Google--Sheets-blue)

## 🚀 Key Features

- **Real-time Stock Deduction:** Automatically deducts inventory when orders are placed on WooCommerce.
- **Low-Stock Alerts:** Instant Gmail notifications when items drop below a custom threshold.
- **Daily Restock Reports:** Automated 8 AM summaries of all low-stock items.
- **Auto-Ordering & Approval:** Direct supplier emails for auto-order items and manual approve/reject links for others.
- **Restock Confirmation:** Seamlessly updates stock via a Tally form and notifies the team on Slack.
- **Centralized Error Monitoring:** A robust global error handler that logs failures and alerts the admin.

## 📂 Project Structure

- `workflow/`: Contains the n8n `.json` files for the main and error workflows.
- `data/`: Local Excel version of the inventory database (`Woocommerce Inventory Management.xlsx`).
- `screenshot/`: Visual flow diagrams of the automation logic.
- `architecture.md`: Detailed technical design and data flow diagrams.

## 🛠️ Tech Stack

- **n8n:** Orchestration and business logic.
- **Google Sheets:** Centralized inventory database and logs.
- **WooCommerce:** Source of sales data.
- **Tally.so:** Form for receiving new inventory.
- **Slack:** Team communication.
- **Gmail:** Supplier and admin notifications.

## 📋 Setup & Installation

1.  **n8n Import:**
    - Import `Inventory Management.json` and `Inventory Management - Error Workflow.json` into your n8n instance.
2.  **Credentials:**
    - Set up OAuth2 credentials for **Google Sheets**, **Gmail**, **Slack**, and **WooCommerce**.
3.  **Google Sheets Database:**
    - Create a sheet with three tabs: `Inventory`, `Orders log`, and `Error Logs`.
    - Map the sheet IDs in the n8n nodes.
4.  **Webhooks:**
    - Register the n8n webhook URLs in WooCommerce (Order Created/Updated) and Tally.
5.  **Environment Variables:**
    - Update the `N8N_BASE_URL` in the **Code** nodes to match your instance.

## 🎥 Demo

Check out the demo video: `https://www.loom.com/share/a5014b41a78b49ffa7d23efd52c9b66a` for a full walkthrough of the system.
