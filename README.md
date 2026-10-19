# SIBIS - Smart Inventory & Business Insight System

**An AI-enabled, full-stack retail management platform for inventory control, point-of-sale operations, procurement management, and data-driven business insights.**

<p align="center">

  **Live Demo:** https://sibis-bd.netlify.app/

  **Backend API:** https://sibis-backend.onrender.com
  
</p>

---

## Overview

SIBIS (Smart Inventory & Business Insight System) is a full-stack business management platform designed to simplify retail operations by bringing inventory management, sales processing, purchasing, supplier management, reporting, and business analytics into one centralized system.

The platform supports multiple stores, role-based access control, automated stock updates, purchase order workflows, and AI-powered business insights. Its forecasting and recommendation features help store owners make informed decisions about inventory replenishment and product demand.

SIBIS combines a React-based frontend, a Node.js and Express backend, MongoDB for data storage, and a Python-based AI/ML service integrated with Google's Gemini API.

## Live Deployment

| Component | Platform | Link |
|---|---|---|
| Frontend | Netlify | [Open SIBIS](https://sibis-bd.netlify.app/) |
| Backend | Render | [Backend Server](https://sibis-backend.onrender.com) |
| Database | MongoDB Atlas | [MongoDB Cloud](https://cloud.mongodb.com/) |

> **Note:** MongoDB Atlas is the database management platform. Access to the actual database requires authorized credentials.

## Key Features

### 1. Authentication & User Management

- JWT-based authentication with token expiration.
- Password hashing using bcrypt.
- Email verification using a six-digit OTP during store registration.
- OTP expiration after 10 minutes.
- Firebase Authentication support and Firebase UID synchronization.
- User profiles with avatar, phone number, bio, and account status.
- Automatic assignment of the Owner role to the first user.

### 2. Role-Based Access Control (RBAC)

SIBIS supports five user roles with different permissions.

| Role | Responsibilities |
|---|---|
| System Admin | Platform-wide store management, platform statistics, and administrative monitoring |
| Owner | Store operations, staff management, purchasing approvals, and business oversight |
| Manager | Operational management, purchase order approvals, and business monitoring |
| Cashier | Point-of-sale operations and sales processing |
| Inventory Staff | Product and inventory operations, stock updates, and purchase order preparation |

Role-based permissions help restrict access to features according to each user's responsibilities.

### 3. Multi-Store Management

- Register and manage multiple stores.
- Store information includes name, address, city, country, and business type.
- Automatically generated store codes.
- Store status management: Active, Suspended, and Trial.
- Subscription plan support: Starter, Pro, and Enterprise.
- Store-specific data isolation.
- Owner-to-store association.

### 4. Dashboard & Business Analytics

- Centralized business dashboard.
- Sales, revenue, and product overview.
- Performance charts and graphical summaries.
- Platform-wide statistics for System Admin.
- Store-level business monitoring.

### 5. Point of Sale (POS)

- Multi-item shopping cart.
- Stock validation before completing a sale.
- Automatically generated invoice numbers.
- Multiple payment methods: Cash, Card, Mobile Pay, and Split Payment.
- Paid and Pending payment statuses.
- Automatic inventory deduction after a sale.
- Integration between sales records and inventory history.

### 6. Product & Inventory Management

- Create, view, update, and delete products.
- SKU and barcode support.
- Product category and brand management.
- Purchase price and selling price tracking.
- Minimum stock threshold configuration.
- Product expiration tracking.
- Alerts for products expiring within 30 days.
- Fixed-amount and percentage-based discounts.
- Discount expiration and effective-price calculation.

### 7. Inventory History & Audit Logs

Track important inventory changes, including:

- Sales.
- Purchases.
- Stock In.
- Stock Out.
- Manual Stock Adjustments.

These records help users monitor inventory movements and review historical changes.

### 8. Smart Reordering & Demand Forecasting

- Automatic low-stock detection.
- Centralized reorder list.
- Supplier-linked reorder suggestions.
- AI-assisted reorder quantity calculation.
- Seven-day demand forecasting using Linear Regression.
- Moving-average fallback when historical data is limited.
- Forecast-based support for inventory replenishment decisions.

### 9. Supplier Management

- Create, view, update, and delete supplier records.
- Store supplier names, contact persons, and phone numbers.
- Link suppliers with products.
- Associate suppliers with purchase orders.

### 10. Purchase Order Management

SIBIS provides a structured purchase order workflow.

**Purchase Order Status Flow:**

`Draft → Ordered → Received`

A purchase order may also be marked as `Cancelled`.

Features include:

- Automatically generated purchase order numbers.
- Draft preparation by Inventory Staff.
- Order approval and status management according to role permissions.
- Stock updates when an order is received.
- Automatic inventory log creation after receiving stock.
- Supplier references for procurement tracking.

### 11. Staff Management

- Add and remove store staff.
- Assign user roles.
- Activate or deactivate staff accounts.
- Monitor staff activity.
- Support controlled access to store operations.

### 12. Store Calendar

- Create custom calendar events.
- Track product expiration dates.
- Manage holiday-related events.
- Display weather-related events.
- Track reorder-related events.
- Support Google Calendar event IDs.

### 13. Notifications

The notification system supports alerts for:

- Low-stock products.
- Expiring products.
- Purchase order status changes.
- Platform-wide system notifications.

### 14. Reports & Business Performance

- Sales performance reports.
- Revenue and profit analysis.
- Inventory reports.
- Business performance monitoring.
- Support for data-driven operational decisions.

### 15. Store Activity Monitoring

The activity audit system records important operational events, including:

- POS sales, invoice details, amounts, and items.
- Inventory stock-in and stock-out activities.
- Discount applications.
- Purchase order creation, receipt, and cancellation.
- Staff additions and removals.
- Relevant system events.

### 16. Platform Administration

The System Admin can access platform-level management features, including:

- View registered stores.
- Monitor store product counts, sales, and revenue.
- Create stores and associate owners.
- Manage store statuses.
- Review platform logs and staff logs.
- View platform statistics for stores, products, users, and revenue.

## AI & Machine Learning Features

SIBIS integrates a Python-based AI/ML service with Google's Gemini API to support forecasting, business analysis, and conversational assistance.

### 1. Demand Forecasting

- Uses Linear Regression to estimate product demand for the next seven days.
- Uses moving-average calculations when available historical data is insufficient.
- Supports suggested reorder quantities.
- Uses Gemini API integration with a local Python calculation fallback.

### 2. Business Insights Engine

The insights engine analyzes available business and inventory information to identify:

- Potential stock-out risks.
- Products running low, including a three-day warning.
- Slow-moving products with no sales in 30 days.
- Products with the highest profit margins.
- Top-selling products over the last seven days.
- AI-generated executive summaries using Gemini.

### 3. SIBIS AI Advisor

The AI Advisor provides a conversational interface for business-related questions and recommendations.

Features include:

- Google Gemini 1.5 Flash integration.
- Recent conversation context using the last eight messages.
- Google Search Grounding support.
- Store-specific context, including stock levels, sales, and weather.
- Bangladesh-specific contextual information, including festivals, weather, supply-chain alerts, and expiration concerns.
- Rule-based local fallback responses.
- Markdown-formatted responses.
- Quick suggestion chips.
- Typing animation and a Stop button.

These features are designed to help users understand business conditions and make better-informed operational decisions.

## Technology Stack

| Category | Technologies |
|---|---|
| Frontend | React.js, Vite, Tailwind CSS, Lucide Icons |
| Backend | Node.js, Express.js |
| Database | MongoDB, Mongoose ODM |
| Authentication | JWT, bcrypt, Firebase Authentication support |
| AI/ML Service | Python, FastAPI |
| Machine Learning | scikit-learn, pandas, NumPy |
| Generative AI | Google Gemini 1.5 Flash API |
| PDF Generation | fpdf2 |
| Frontend Deployment | Netlify |
| Backend Deployment | Render |
| Database Hosting | MongoDB Atlas |

## System Architecture

The system uses a frontend, backend API, database, and AI/ML service to support its main operations.

```text
                 ┌────────────────────────┐
                 │       User / Staff     │
                 └────────────┬───────────┘
                              │
                              ▼
                 ┌────────────────────────┐
                 │   React + Vite Client  │
                 │        Netlify         │
                 └────────────┬───────────┘
                              │
                              ▼
                 ┌────────────────────────┐
                 │   Node.js + Express    │
                 │      Render API        │
                 └───────┬────────┬───────┘
                         │        │
                ┌────────▼───┐  ┌─▼────────────────┐
                │  MongoDB   │  │ Python FastAPI   │
                │   Atlas    │  │ AI/ML Service    │
                └────────────┘  └────────┬─────────┘
                                         │
                                    ┌────▼─────────┐
                                    │ Gemini API   │
                                    └──────────────┘
```

The diagram represents the intended high-level architecture. Actual service communication depends on the deployed application configuration.

## Database Collections

The project uses MongoDB collections for the following data entities:

- `users` — User accounts and roles.
- `stores` — Store information and settings.
- `products` — Product and inventory details.
- `sales` — Sales transactions.
- `suppliers` — Supplier records.
- `purchaseorders` — Purchase order information.
- `inventorylogs` — Inventory movement history.
- `activitylogs` — Store activity records.
- `platformlogs` — Platform-level administrative logs.
- `calendarevents` — Store calendar events.

## Demo Accounts

You can explore SIBIS using the following role-based demonstration accounts.

| Role | Email | Password |
|---|---|---|
| System Admin (Platform Super Admin) | `admin@sibis.com` | `admin123` |
| Store Owner | `owner@sibis.com` | `password123` |
| Store Manager | `manager@sibis.com` | `password123` |
| Cashier | `cashier@sibis.com` | `password123` |
| Inventory Staff | `inventory@sibis.com` | `password123` |

**To get started:**

1. Open the [SIBIS Live Application](https://sibis-bd.netlify.app/).
2. Sign in using the credentials for the role you want to explore.
3. Explore the features available to that role.

> **Security notice:** These credentials are published for demonstration purposes. They should only be used for non-sensitive demo accounts. Do not publish production credentials, API keys, private tokens, or database connection strings in a public repository.

## Getting Started

To run SIBIS locally, you need the source code and the configuration required by each service.

### Prerequisites

- Node.js and npm.
- MongoDB instance or MongoDB Atlas account.
- Python environment for the AI/ML service.
- Google Gemini API key for Gemini-powered features.
- Firebase configuration if Firebase authentication features are enabled.

### Installation

Clone the repository:

```bash
git clone https://github.com/MdMoonRahmanNayem/Smart-Inventory-Business-Insight-System-SIBIS-.git
cd Smart-Inventory-Business-Insight-System-SIBIS-
```

Install the frontend and backend dependencies from their respective project directories.

```bash
npm install
```

For the Python AI/ML service, install the dependencies listed in its `requirements.txt` file, if provided.

```bash
pip install -r requirements.txt
```

**Important:** The exact directory names, environment variables, and startup commands depend on the repository's current structure. Run these commands from the appropriate directories and follow the configuration files in the source code.

### Environment Configuration

Configure the required environment variables using the names expected by the application.

Typical configuration may include:

- MongoDB connection URI.
- JWT secret.
- Gemini API key.
- Firebase credentials or configuration.
- Frontend API base URL.
- Backend port and service URLs.

Do not commit `.env` files, secrets, or production credentials to GitHub. Use the deployment platform's environment-variable settings for deployed services.

## Security Considerations

- Passwords are hashed using bcrypt.
- JWT is used for authentication.
- Role-based access control separates user permissions.
- Store-specific data isolation supports multi-store operations.
- Email OTP verification supports store registration.
- Sensitive configuration values should be stored in environment variables.

Security features should always be reviewed and tested against the actual deployed implementation before production use.

## Future Improvements

Potential areas for future development include:

- More advanced demand forecasting models.
- Expanded sales and inventory analytics.
- Additional integrations with accounting and e-commerce systems.
- More comprehensive automated testing.
- Enhanced monitoring and performance optimization.
- Improved backup, recovery, and operational security workflows.

## Project Links

- **Live Application:** https://sibis-bd.netlify.app/
- **GitHub Repository:** https://github.com/MdMoonRahmanNayem/Smart-Inventory-Business-Insight-System-SIBIS-
- **Backend API:** https://sibis-backend.onrender.com
- **MongoDB Atlas:** https://cloud.mongodb.com/

---

## Author

**SIBIS — Smart Inventory & Business Insight System**

A full-stack software engineering project combining retail management, inventory automation, business analytics, and AI-assisted decision support.

