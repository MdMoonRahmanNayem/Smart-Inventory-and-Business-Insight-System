# SIBIS - Smart Inventory & Business Insight System

> A full-stack retail management platform for managing inventory, sales, purchases, suppliers, reporting, and AI-assisted business insights in one centralized system.

---

## Live Demo: https://sibis-bd.netlify.app/ 

---

## Overview

**SIBIS (Smart Inventory & Business Insight System)** is a web-based retail management platform developed to simplify day-to-day operations for small and medium-sized retail businesses.

The system brings essential retail activities into a single platform, including product and inventory management, point-of-sale operations, purchase management, supplier management, dashboards, reports, user management, and AI-assisted business insights.

SIBIS is designed for businesses such as grocery stores, mini marts, pharmacies, and other local retail shops where maintaining accurate inventory records and monitoring business performance are important for daily operations.

The system connects sales and purchasing activities with inventory updates, allowing stock information to remain synchronized with business transactions. It also integrates the **Google Gemini API** to generate business summaries and insights from relevant business data.

---

## Problem

Small retail businesses often manage inventory, sales, purchases, and supplier information using manual records, spreadsheets, or separate systems.

This can lead to:

- Inaccurate stock records
- Difficulty tracking sales and purchases
- Manual inventory updates
- Limited visibility into business performance
- Difficulty identifying low-stock products
- Scattered supplier and product information
- Time-consuming business reporting

SIBIS addresses these problems by bringing the major retail operations into one connected system.

---

## What SIBIS Provides

SIBIS provides a centralized workflow for managing the major activities of a retail business.

### Inventory
Manage products, categories, stock quantities, stock thresholds, and inventory activities from one place.

### Sales & POS
Process customer purchases through a dedicated POS interface while automatically updating the related inventory.

### Purchase Management
Create and manage purchase orders, track their status, and update inventory when purchased products are received.

### Supplier Management
Maintain supplier information and associate suppliers with purchasing and product-related activities.

### Dashboard & Reports
View important business information through dashboards and organized reports.

### User Management
Manage users according to their assigned roles and permissions.

### AI Business Insights
Use the Google Gemini API to generate business summaries and insights based on available business information.

---

## Key Features

### Authentication & Role-Based Access

SIBIS supports multiple user roles with different levels of access:

- System Administrator
- Store Owner
- Store Manager
- Cashier
- Inventory Staff

Authentication is handled using **Firebase Authentication**, while backend authorization controls access to protected operations.

---

### Product Management

The product management module provides centralized management of product information.

Users with appropriate permissions can:

- Add products
- Edit products
- Delete products
- Search products
- Manage product categories
- Maintain purchase and selling prices
- Set stock-related thresholds
- Maintain supplier information
- Manage expiry-related product information

---

### Inventory Management

The inventory module keeps track of the current stock status of products.

Key operations include:

- Monitoring available stock
- Updating stock quantities
- Managing stock adjustments
- Identifying low-stock products
- Tracking inventory activities
- Handling stock updates from sales
- Handling stock updates from received purchases
- Monitoring applicable expiry information

Inventory changes are connected with sales and purchase operations to reduce manual stock updates.

---

### Point of Sale (POS)

The POS module is designed for fast and organized sales processing.

Cashiers can:

- Search for products
- Add products to a transaction
- Adjust quantities
- Calculate transaction totals
- Record customer purchases
- Process payment information
- Generate invoices
- Complete sales transactions

After a sale is completed, the corresponding product stock is updated automatically.

---

### Purchase Management

The purchase module manages the procurement workflow.

It supports:

- Creating purchase orders
- Managing purchase order details
- Tracking purchase order status
- Receiving purchased products
- Updating inventory after receiving products
- Connecting purchases with suppliers

This provides a structured process for managing product procurement.

---

### Supplier Management

The supplier module provides a centralized location for supplier records.

It supports:

- Adding suppliers
- Updating supplier information
- Managing supplier records
- Connecting suppliers with products
- Maintaining supplier-related purchase information

---

### Dashboard

The dashboard provides an overview of important business information.

Depending on the user's access level, the dashboard can provide information related to:

- Sales
- Revenue
- Gross margin
- Products
- Inventory
- Low-stock products
- Business activities

This allows owners and managers to quickly review the current state of the business.

---

### Reports

SIBIS provides reporting functionality for reviewing business activities.

Reports cover areas including:

- Inventory
- Sales
- Purchases
- Business performance

The reporting functionality helps users review operational data and make informed decisions.

---

### Notifications

The system provides inventory-related notifications and alerts to draw attention to conditions that require action.

Examples include:

- Low-stock notifications
- Expiry-related notifications
- Inventory warnings

---

## AI Integration

SIBIS integrates the **Google Gemini API** to provide AI-assisted business insights.

The AI functionality works with relevant business information available in the system and generates understandable summaries that help users review their business data.

### AI Flow

```text
React Frontend
      │
      ▼
Node.js + Express Backend
      │
      ▼
Business Data
      │
      ▼
Google Gemini API
      │
      ▼
Business Summary / Insight
      │
      ▼
React Frontend
````

The Gemini API is accessed through the backend rather than directly from the frontend.

This keeps the AI integration within the server-side application and allows the backend to control the data sent to the external AI service.

---

## System Architecture

SIBIS follows a client-server architecture with separate frontend, backend, database, authentication, and AI components.

```text
                    ┌──────────────────────┐
                    │       Users          │
                    │ Owner / Manager      │
                    │ Cashier / Staff      │
                    │ Administrator        │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │    React Frontend    │
                    │     Tailwind CSS     │
                    └──────────┬───────────┘
                               │
                             REST API
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Node.js + Express  │
                    │       Backend        │
                    └───────┬───────┬──────┘
                            │       │
                            │       ▼
                            │  ┌───────────────┐
                            │  │ Google Gemini │
                            │  │      API      │
                            │  └───────────────┘
                            │
                            ▼
                    ┌──────────────────────┐
                    │       MongoDB        │
                    │       Database       │
                    └──────────────────────┘
```

---

## Technology Stack

| Layer             | Technologies                   |
| ----------------- | ------------------------------ |
| Frontend          | React.js, Vite, Tailwind CSS   |
| Routing           | React Router                   |
| API Communication | Axios / REST API               |
| Backend           | Node.js, Express.js            |
| Database          | MongoDB, Mongoose              |
| Authentication    | Firebase Authentication        |
| Authorization     | JWT, Firebase Admin SDK        |
| AI Integration    | Google Gemini API              |
| Security          | Helmet                         |
| Logging           | Morgan                         |
| Development       | Git, GitHub, VS Code, Postman  |
| Deployment        | Netlify, Render, MongoDB Atlas |

---

## Project Structure

```text
SIBIS/
│
├── backend/
│   ├── src/
│   │   ├── config/
│   │   │   ├── db.js
│   │   │   ├── firebase.js
│   │   │   ├── seed.js
│   │   │   └── seed_200_products.js
│   │   │
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── utils/
│   │   └── app.js
│   │
│   ├── migrate.js
│   ├── package.json
│   ├── scratch_api_test.js
│   └── scratch_test.js
│
├── frontend/
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   ├── config/
│   │   ├── context/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── App.css
│   │   ├── index.css
│   │   └── main.jsx
│   │
│   ├── package.json
│   └── vite.config.js
│
├── check_workspace.js
├── package.json
└── README.md
```

---

## Backend Structure

The backend follows a modular structure to keep API handling and business logic organized.

```text
backend/
└── src/
    ├── config/
    ├── controllers/
    ├── middleware/
    ├── models/
    ├── routes/
    ├── utils/
    └── app.js
```

### Main Backend Layers

**Config**
Contains database, Firebase, and related application configuration.

**Controllers**
Handles the business logic associated with API operations.

**Middleware**
Handles authentication, authorization, and request-level processing.

**Models**
Defines MongoDB data models using Mongoose.

**Routes**
Defines the REST API endpoints used by the frontend.

**Utils**
Contains reusable backend utilities.

---

## Frontend Structure

The frontend uses a component-based React architecture.

```text
frontend/
└── src/
    ├── assets/
    ├── components/
    ├── config/
    ├── context/
    ├── pages/
    ├── services/
    ├── App.css
    ├── index.css
    └── main.jsx
```

### Main Frontend Layers

**Components**
Reusable UI components used throughout the application.

**Pages**
Individual application screens for different modules and user roles.

**Context**
Application-wide state and authentication-related context.

**Services**
Handles communication between the frontend and backend APIs.

**Config**
Contains frontend configuration.

---

## User Roles

### System Administrator

Responsible for platform-level administration and user-related management.

### Store Owner

Has access to overall business information, dashboards, reports, and store management functionality.

### Store Manager

Handles day-to-day store operations, including inventory, purchasing, and other operational activities.

### Cashier

Handles customer sales and POS transactions.

### Inventory Staff

Handles product and inventory-related operations and monitors stock conditions.

---

## API Overview

The backend provides REST APIs for the major modules of SIBIS.

```text
/api/users
/api/products
/api/sales
/api/purchase-orders
/api/suppliers
/api/ai
/api/admin
```

The frontend communicates with these APIs to perform application operations and retrieve business information.

---

## Database

SIBIS uses **MongoDB** as its primary database with **Mongoose** as the ODM layer.

The database manages information related to:

* Users
* Products
* Categories
* Suppliers
* Inventory
* Sales
* Purchase Orders
* Business activities
* Transaction records

For production deployment, the application uses **MongoDB Atlas**.

---

## Authentication & Security

SIBIS uses multiple mechanisms for authentication and access control.

### Firebase Authentication

Used for user authentication and identity management.

### JWT

Used for authenticated backend requests and authorization-related processing.

### Firebase Admin SDK

Used on the backend for server-side Firebase authentication handling.

### Role-Based Authorization

Protected backend operations verify user roles before allowing access to restricted functionality.

### Helmet

The Express backend uses Helmet to add security-related HTTP headers.

---

## Testing

Testing was performed across the major application components to verify that the system works correctly as an integrated platform.

Testing activities include:

* API testing
* Authentication testing
* Role-based access testing
* Database operation testing
* Inventory transaction testing
* POS testing
* Purchase workflow testing
* Frontend-backend integration testing
* Deployment testing

**Postman** was used for testing and verifying backend APIs.

---

## Development Process

SIBIS was developed following the Software Development Life Cycle (SDLC).

The project development process covered:

```text
Requirement Analysis
        ↓
Software Requirements Specification
        ↓
System & Architecture Design
        ↓
Database & UML Design
        ↓
Implementation
        ↓
Testing & Debugging
        ↓
Deployment
        ↓
Documentation
```

The project includes software engineering artifacts such as:

* Use Case Diagram
* Activity Diagrams
* Architectural Diagrams
* Component Diagrams
* Class Diagram
* ER Diagram
* Navigation Flow Diagram
* UI Designs

---

## Local Setup

### Prerequisites

Make sure the following are installed:

* Node.js
* npm
* Git
* MongoDB / MongoDB Atlas
* Firebase project
* Google Gemini API access

### Clone the Repository

```bash
git clone https://github.com/SarafatAlamIrfan/SIBIS.git
cd SIBIS
```

### Backend

```bash
cd backend
npm install
```

Create the required `.env` configuration and add your database, authentication, and Gemini API credentials.

Start the backend:

```bash
npm start
```

### Frontend

Open another terminal:

```bash
cd frontend
npm install
```

Configure the required frontend environment variables.

Start the development server:

```bash
npm run dev
```

The local application can then be accessed through the URL provided by Vite.

---

## Environment Configuration

Sensitive credentials should be stored in environment variables rather than committed to the repository.

### Backend

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
JWT_EXPIRES_IN=30d
GEMINI_API_KEY=your_gemini_api_key
```

### Frontend

```env
VITE_FIREBASE_API_KEY=your_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_auth_domain
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_storage_bucket
VITE_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
VITE_FIREBASE_APP_ID=your_app_id
VITE_FIREBASE_MEASUREMENT_ID=your_measurement_id
VITE_API_URL=your_backend_api_url
```

The exact values depend on the Firebase project, database, backend deployment, and API configuration being used.

---

## Deployment

SIBIS uses a separate deployment setup for its frontend, backend, and database.

| Component | Deployment    |
| --------- | ------------- |
| Frontend  | Netlify       |
| Backend   | Render        |
| Database  | MongoDB Atlas |

The frontend communicates with the deployed backend through the configured API endpoint.

---

## Future Scope

The following areas can be considered for future versions of SIBIS:

* Multi-store inventory management
* Mobile application development
* Advanced AI forecasting
* Payment integration
* Accounting integration

These are future enhancements and are not part of the current core implementation.

---

## Project Highlights

* Full-stack web application
* Modular frontend and backend architecture
* Role-based access control
* Real-time inventory updates through business transactions
* Integrated POS system
* Purchase and supplier management
* Business dashboards and reporting
* Firebase-based authentication
* MongoDB-based data management
* Google Gemini API integration
* RESTful backend APIs
* Cloud deployment

---
