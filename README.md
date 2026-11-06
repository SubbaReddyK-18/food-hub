# 🍔 FoodHub – MERN Stack Gourmet Food Ordering & Delivery Application

> **MERN Stack Web Development Training Program – Final Capstone Project**  
> A full-stack, responsive, high-performance gourmet food ordering web application with customer ordering workflows, live order tracking, and an administrative control portal.

---

## 👥 Team Information

* **Team Name:** **TEAM TISSOT**  
* **GitHub Repository:** [https://github.com/SubbaReddyK-18/food-hub](https://github.com/SubbaReddyK-18/food-hub)  
* **Live Deployment Link:** `[Insert Deployed URL Here - e.g., https://food-hub-three.vercel.app]`

| S.No | Team Member Name | Registration Number | Role / Key Contribution |
| :---: | :--- | :--- | :--- |
| **1** | **D.L. Ganesh** | `241FA04A55` | Frontend UI Development & Routing |
| **2** | **P. Anand Babu** | `241FA04A60` | Backend API & Controller Services |
| **3** | **T. Kowsik** | `241FA04A65` | Database Schema & MongoDB Integration |
| **4** | **K. Subba Reddy** | `241FA04B47` | Full-Stack Integration, Auth & Deployment |

---

## 📖 Project Overview

**FoodHub** is an end-to-end full-stack web application designed to simulate modern food delivery services like DoorDash, Zomato, and UberEats. It bridges the gap between food lovers seeking artisanal gourmet dishes and restaurant managers tracking live kitchen orders.

The application incorporates a rich frontend built with React and Tailwind CSS, an Express.js and Node.js REST API layer, and a robust MongoDB database supporting comprehensive CRUD capabilities, secure JWT authentication, role-based authorization, and real-time status progression.

---

## 🎯 Project Objectives

1. **Full-Stack MERN Integration:** Establish seamless communication between React frontend, Express/Node backend, and MongoDB database.
2. **Comprehensive CRUD Operations:** Enable full lifecycle data management for food menu items, customer carts, and active customer orders.
3. **Role-Based Access Control (RBAC):** Provide distinct interfaces and permissions for regular customers vs. administrative staff.
4. **Intuitive Customer Experience:** Deliver dynamic search, dietary filters (Veg / Non-Veg), category-based navigation, cart management, promo codes, and Cash on Delivery (COD) checkout.
5. **Kitchen & Order Management:** Give administrators real-time analytical KPIs (revenue, order counts, average order values) and status fulfillment tools (`Placed` ➔ `Preparing` ➔ `On the way` ➔ `Delivered`).
6. **Production-Ready Deployment:** Deploy the entire stack to the cloud with live database connectivity and continuous availability.

---

## 💻 Technologies Used (MERN Stack)

| Layer | Technology | Purpose & Details |
| :--- | :--- | :--- |
| **M – Database** | **MongoDB (Atlas & Compass)** | NoSQL document database storing user accounts, food menu catalogs, and customer orders with high availability. |
| **E – Backend Framework** | **Express.js** | Lightweight web application framework handling RESTful routing, CORS, JWT middleware, and API controllers. |
| **R – Frontend Library** | **React.js 18 (Vite)** | Fast single-page application (SPA) with responsive UI built using **Tailwind CSS**, **Lucide React** icons, and **React Router DOM**. |
| **N – Runtime Environment** | **Node.js 20+** | Scalable JavaScript runtime executing server-side logic and database operations. |

### Additional Libraries & Tools
- **State Management:** React Context API (`AuthContext`, `CartContext`)
- **Authentication:** `jsonwebtoken` (JWT) and `bcryptjs` for secure password hashing
- **Styling:** Tailwind CSS with PostCSS & Autoprefixer
- **Presentation:** PowerPoint slides generated with `pptxgenjs` (`FoodHub_Project_Presentation.pptx`)

---

## 🔄 CRUD Operations Matrix

The application strictly implements **Create, Read, Update, and Delete** operations across its core modules:

| Module | Create (POST) | Read (GET) | Update (PUT/PATCH) | Delete (DELETE) |
| :--- | :--- | :--- | :--- | :--- |
| **Food Dishes** | Admin adds new dishes with images, description, price, & category | Customers/Admin browse menu, filter by category/veg, view dish details | Admin edits dish price, name, category, or description in real-time | Admin deletes retired dishes from the catalog |
| **Customer Orders** | Customer places a new COD order at checkout | View past and active orders in Order History & Admin order fulfillment | Admin updates live order status (`Placed` ➔ `Preparing` ➔ `Delivered`) | Customer or Admin cancels an order |
| **User Authentication** | New user registers (Customer or Admin) | Fetch user profile via token verification (`/api/auth/me`) | Update user profile and address details | Admin manages user accounts |
| **Shopping Cart** | Add dishes to cart with selected quantity | View itemized cart, subtotal, 8% tax, and shipping fee | Increase/decrease quantity with real-time recalculation | Remove single item or clear entire cart |

---

## 🌟 Features and Functionalities

### 🛍️ 1. Customer Portal
- **Hero & Landing Page:** Interactive showcase with quick search, chef recommendations, popular dishes, and testimonials.
- **Categorized Menu Catalog:** Filter by category (*Burgers, Pizza, Pasta, Asian, Bowls, Sides, Desserts, Beverages*).
- **Dietary Filter:** Instant toggle for **Pure Vegetarian** dishes.
- **Food Details Page:** High-resolution photography, dietary indicators, prep time, and dynamic quantity selector.
- **Dynamic Shopping Cart:** Free delivery threshold ($40+), 8% tax calculation, and coupon codes (`WELCOME30`, `FOODHUB10`).
- **Smooth Checkout:** Delivery address with apartment & driver notes, Cash on Delivery confirmation, and instant order creation.
- **Live Order Status Tracker:** Real-time visual progress tracker (`Placed` ➔ `Preparing` ➔ `On the way` ➔ `Delivered`).
- **Authentication:** Register and login with secure JWT tokens, plus **1-click quick demo login buttons**.

### 🛡️ 2. Admin Control Portal
- **Dashboard Analytics:** Live summary cards displaying Total Revenue, Total Orders Placed, Active Dishes, and Average Order Value.
- **Food Catalog Management (CRUD):** Add new food items, live inline edit existing dishes, and delete retired menu items.
- **Order Fulfillment Board:** Track customer delivery addresses, customer phone numbers, itemized breakdown, and update dispatch status.

---

## 🏗️ System Architecture

```text
┌────────────────────────────────────────────────────────┐
│             React Single Page Application              │
│       (Vite + Tailwind CSS + React Router DOM)         │
└───────────────────────────┬────────────────────────────┘
                            │
               RESTful HTTP Requests (JSON)
                            │
┌───────────────────────────▼────────────────────────────┐
│                  Express.js / Node.js                  │
│  (Auth Middleware, JWT Verification, Route Controllers)│
└───────────────────────────┬────────────────────────────┘
                            │
              Mongoose / MongoDB Native Driver
                            │
┌───────────────────────────▼────────────────────────────┐
│              MongoDB Database (Atlas / Compass)        │
│          Collections: `users`, `foods`, `orders`       │
└────────────────────────────────────────────────────────┘
```

---

## 📂 Project Folder Structure

```text
food-hub/
├── api/                           # Vercel Serverless Function Endpoints
│   ├── _lib/
│   │   ├── auth.js                # JWT verification & bcrypt hashing
│   │   └── db.js                  # MongoDB Atlas connection pooling
│   ├── auth/                      # Register, Login, Me endpoints
│   ├── foods/                     # Food CRUD endpoints
│   └── orders/                    # Order placement & fulfillment endpoints
├── scripts/
│   ├── seed.js                    # MongoDB database seeder script
│   └── inspect-db.js              # Database diagnostics utility
├── server/                        # Express.js Standalone Backend Server
│   ├── routes/
│   │   ├── auth.js                # Auth routes
│   │   ├── foods.js               # Food catalog CRUD routes
│   │   ├── orders.js              # Order routes
│   │   └── test.js                # Health & DB diagnostic routes
│   ├── db.js                      # MongoDB connection handler
│   └── index.js                   # Express server entry point (port 5000)
├── src/                           # React Frontend Application
│   ├── components/                # Reusable UI (Navbar, Footer, FoodCard, SearchBar)
│   ├── context/                   # Global State (AuthContext, CartContext)
│   ├── pages/                     # App Pages (Home, Menu, Cart, Checkout, Orders, Admin)
│   ├── services/                  # API client service & fallback mock data
│   ├── App.jsx                    # Route definitions
│   └── main.jsx                   # React DOM root
├── FoodHub_Presentation.html      # Interactive HTML presentation
├── FoodHub_Project_Presentation.pptx # 10-slide PowerPoint presentation
├── .env.example                   # Environment variables template
├── package.json                   # Project scripts and dependencies
├── tailwind.config.js             # Tailwind CSS configuration
├── vite.config.js                 # Vite build & proxy configuration
└── README.md                      # Complete project documentation
```

---

## ⚙️ Environment Configuration

Create a `.env` file in the project root:

```env
# MongoDB Connection String (Atlas Cloud or Local Compass)
MONGODB_URI=mongodb://127.0.0.1:27017/foodhub
# or for MongoDB Atlas:
# MONGODB_URI=mongodb+srv://<user>:<password>@cluster0.mongodb.net/?retryWrites=true&w=majority

MONGODB_DB=foodhub
JWT_SECRET=your_super_secret_jwt_key_2026
PORT=5000
```

---

## 🚀 Installation & Execution Steps

### 1. Clone the Repository
```bash
git clone https://github.com/SubbaReddyK-18/food-hub.git
cd food-hub
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Seed the Database
Ensure your MongoDB instance is running (locally or on MongoDB Atlas), then populate default dishes and accounts:
```bash
npm run seed
```
> **Default Test Accounts:**
> - **Admin:** `admin@foodhub.com` / `admin123`
> - **Customer:** `customer@foodhub.com` / `customer123`

### 4. Run the Application

#### Option A: Full-Stack Mode (Express Backend + React Frontend)
* **Terminal 1 (Backend):**
  ```bash
  npm run server
  ```
  *Server starts at `http://localhost:5000`*

* **Terminal 2 (Frontend):**
  ```bash
  npm run dev
  ```
  *Frontend starts at `http://localhost:3000`*

#### Option B: Production Single-Server Mode
```bash
npm run build
npm start
```
*Access the unified full-stack application at `http://localhost:5000`*

---

## 🌐 Deployment Instructions

### Deploy to Vercel (Frontend + Serverless Backend)
1. Push this repository to GitHub.
2. Sign in to [Vercel](https://vercel.com) and click **"Add New Project"** ➔ Import `SubbaReddyK-18/food-hub`.
3. In **Settings ➔ Environment Variables**, add:
   - `MONGODB_URI`: Your MongoDB Atlas connection URI
   - `MONGODB_DB`: `foodhub`
   - `JWT_SECRET`: Any random secure secret string
4. Click **Deploy**. Vercel will build the React Vite frontend and automatically deploy `/api/*` endpoints as serverless functions.
5. Copy your live deployment URL (e.g., `https://food-hub-three.vercel.app`) and paste it into the **Team Information** section above.

---

## 📊 Project Presentation

The required project presentation by **TEAM TISSOT** is available in this repository:
- 📑 **PowerPoint Presentation:** [`FOOD HUB.pptx`](./FOOD%20HUB.pptx)
- 🌐 **Interactive Web Slides:** [`FoodHub_Presentation.html`](./FoodHub_Presentation.html)

**Slide Breakdown:**
1. Title Slide (Project Title, Team Members, Registration Numbers)
2. Introduction & Background
3. Problem Statement
4. Project Objectives
5. MERN Stack Technologies Used
6. System Modules (Customer, Cart, Order, Admin)
7. System Architecture & Workflow Diagram
8. Database Schema & Collections Design
9. Implementation & Screenshots
10. Conclusion & Future Enhancements
