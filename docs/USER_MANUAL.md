# USER MANUAL

---

# ECOMMERCE PLATFORM

## Complete User Manual

---

**Project Name:** ECommerce Platform
**Version:** 3.0
**Document Version:** 1.0
**Date:** January 30, 2026

**Team Members:**
- Project Manager: Sarah Johnson
- Lead Developer: Michael Chen
- Frontend Developer: Emily Rodriguez
- Backend Developer: David Kim
- QA Engineer: Jessica Williams
- DevOps Engineer: Robert Taylor
- UI/UX Designer: Amanda Foster
- Database Administrator: Christopher Lee

---

# PREFACE

## About This Document

This User Manual provides comprehensive guidance for using the ECommerce Platform. It is intended for all users including Customers, Sellers, and Administrators who interact with the system.

This document covers:
- System installation and configuration
- Step-by-step instructions for all features
- Troubleshooting common issues
- Frequently asked questions

**Document Conventions:**
- **Bold text** indicates UI elements, buttons, or menu items
- *Italic text* indicates field names or parameters
- `Code formatting` indicates technical values or URLs
- [Insert Screenshot: Title] indicates where screenshots should be placed

**Intended Audience:**
- End Users (Customers)
- Sellers and Merchants
- System Administrators
- Support Staff

---

# TABLE OF CONTENTS

1. Introduction
2. System Overview
3. Architecture Overview
4. Installation Guide
   - 4.1 Prerequisites
   - 4.2 Backend Installation
   - 4.3 Frontend Installation
   - 4.4 Database Configuration
5. Application Workflow
6. Module Instructions
   - 6.1 Authentication Module
   - 6.2 Product Catalog Module
   - 6.3 Shopping Cart Module
   - 6.4 Checkout and Orders Module
   - 6.5 Wishlist Module
   - 6.6 Reviews Module
   - 6.7 User Profile Module
   - 6.8 Seller Dashboard Module
   - 6.9 Admin Dashboard Module
   - 6.10 Premium Subscription Module
7. Troubleshooting
8. FAQs
9. Glossary
10. Appendix

---

# 1. INTRODUCTION

## 1.1 Purpose

The ECommerce Platform is a comprehensive online shopping solution designed to connect customers with sellers in a secure, user-friendly environment. This full-stack application supports three distinct user roles: Customers, Sellers, and Administrators, each with specialized features and capabilities.

## 1.2 Scope

This manual covers all aspects of the ECommerce Platform including:
- Customer shopping experience
- Seller product management and analytics
- Administrative oversight and system configuration
- Payment processing and order management
- Premium subscription services

## 1.3 System Objectives

The platform aims to:
- Provide a seamless shopping experience for customers
- Empower sellers with tools to manage their products and orders
- Give administrators full control over platform operations
- Ensure secure transactions and data protection
- Support scalable growth with robust architecture

---

# 2. SYSTEM OVERVIEW

## 2.1 Platform Description

The ECommerce Platform is a modern, full-stack web application built using enterprise-grade technologies. It features a responsive Angular frontend communicating with a Spring Boot REST API backend, supported by an H2 database for data persistence.

## 2.2 Key Features

### Customer Features
- Browse and search products with advanced filtering
- Product comparison functionality
- Shopping cart management
- Multiple delivery address management
- Coupon code redemption
- Order placement and tracking
- Product reviews and ratings
- Wishlist management
- Recently viewed products tracking
- Premium subscription options

### Seller Features
- Product listing and management
- Inventory control
- Sales dashboard with analytics
- Order fulfillment management
- Payout tracking and requests
- Seller verification process

### Administrator Features
- User and seller management
- Category management
- Coupon creation and management
- Delivery zone configuration
- Platform analytics dashboard
- Order administration
- Payout approval system
- Subscription management

## 2.3 User Roles

| Role | Description | Access Level |
|------|-------------|--------------|
| Customer | End users who browse and purchase products | Standard user access |
| Seller | Merchants who list and sell products | Extended access with product management |
| Administrator | Platform managers with full system control | Full administrative access |

---

# 3. ARCHITECTURE OVERVIEW

## 3.1 System Architecture

The ECommerce Platform follows a three-tier architecture pattern:

### Presentation Layer (Frontend)
```
+--------------------------------------------------+
|                 ANGULAR FRONTEND                  |
|  +--------------------------------------------+  |
|  |  Components  |  Services  |  Guards        |  |
|  +--------------------------------------------+  |
|  |  18 UI       |  9 Data    |  Auth & Role   |  |
|  |  Components  |  Services  |  Guards        |  |
|  +--------------------------------------------+  |
+--------------------------------------------------+
                        |
                        | HTTP/REST
                        |
                        v
```

### Application Layer (Backend)
```
+--------------------------------------------------+
|              SPRING BOOT BACKEND                  |
|  +--------------------------------------------+  |
|  |  26 REST Controllers                       |  |
|  +--------------------------------------------+  |
|  |  42 Business Services                      |  |
|  +--------------------------------------------+  |
|  |  55 Data Transfer Objects (DTOs)          |  |
|  +--------------------------------------------+  |
+--------------------------------------------------+
                        |
                        | JPA/Hibernate
                        |
                        v
```

### Data Layer (Database)
```
+--------------------------------------------------+
|                  H2 DATABASE                      |
|  +--------------------------------------------+  |
|  |  18 JPA Entities                          |  |
|  |  18 Repository Interfaces                 |  |
|  +--------------------------------------------+  |
+--------------------------------------------------+
```

## 3.2 Technology Stack

### Backend Technologies
- **Framework:** Spring Boot 3.2.5
- **Language:** Java 17
- **ORM:** Spring Data JPA with Hibernate
- **Database:** H2 (In-Memory)
- **API Documentation:** SpringDoc OpenAPI 2.5.0
- **Build Tool:** Apache Maven

### Frontend Technologies
- **Framework:** Angular 19.2
- **Language:** TypeScript 5.6.3
- **UI Library:** Angular Material 19.2
- **Reactive Extensions:** RxJS 7.8
- **Build Tool:** Angular CLI / npm

## 3.3 Data Flow Diagram

```
[User Browser]
      |
      v
[Angular Frontend] --HTTP Request--> [Spring Boot API]
      ^                                      |
      |                                      v
      |                              [Service Layer]
      |                                      |
      |                                      v
      |                              [Repository Layer]
      |                                      |
      |                                      v
      +<----HTTP Response---------   [H2 Database]
```

## 3.4 Database Entity Relationships

```
USER (1) -----> (N) PRODUCT [Seller owns products]
USER (1) -----> (1) CART [Each user has one cart]
CART (1) -----> (N) CART_ITEM [Cart contains items]
USER (1) -----> (N) ORDER [User places orders]
ORDER (1) -----> (N) ORDER_ITEM [Order contains items]
PRODUCT (1) -----> (N) REVIEW [Products have reviews]
USER (1) -----> (N) WISHLIST [User's saved items]
CATEGORY (1) -----> (N) PRODUCT [Category groups products]
```

---

# 4. INSTALLATION GUIDE

## 4.1 Prerequisites

Before installing the ECommerce Platform, ensure your system meets the following requirements:

### Hardware Requirements
- **Processor:** Dual-core CPU 2.0 GHz or higher
- **RAM:** 8 GB minimum (16 GB recommended)
- **Storage:** 10 GB free disk space
- **Network:** Stable internet connection

### Software Requirements
- **Operating System:** Windows 10/11, macOS 10.15+, or Linux (Ubuntu 20.04+)
- **Java Development Kit:** JDK 17 or higher
- **Node.js:** Version 18.x or higher
- **npm:** Version 9.x or higher
- **Maven:** Version 3.8 or higher
- **Git:** Version 2.30 or higher
- **Web Browser:** Chrome 90+, Firefox 88+, Safari 14+, or Edge 90+

### Verification Commands

To verify prerequisites, run the following commands:

```bash
java -version      # Should show java 17.x.x
node -version      # Should show v18.x.x or higher
npm -version       # Should show 9.x.x or higher
mvn -version       # Should show Apache Maven 3.8.x
git --version      # Should show git version 2.30.x
```

## 4.2 Backend Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/your-organization/Ecommerce-Claude-Version-3.git
cd Ecommerce-Claude-Version-3
```

[Insert Screenshot: Repository Clone Success]

### Step 2: Navigate to Backend Directory

```bash
cd ecommerce-backend
```

### Step 3: Build the Application

```bash
mvn clean install
```

[Insert Screenshot: Maven Build Success]

### Step 4: Run the Backend Server

```bash
mvn spring-boot:run
```

The backend server will start on `http://localhost:8080`

[Insert Screenshot: Backend Server Running]

### Step 5: Verify Backend Installation

Open a web browser and navigate to:
- Swagger UI: `http://localhost:8080/swagger-ui.html`
- H2 Console: `http://localhost:8080/h2-console`

[Insert Screenshot: Swagger UI Homepage]

## 4.3 Frontend Installation

### Step 1: Navigate to Frontend Directory

Open a new terminal window and navigate:

```bash
cd Ecommerce-Claude-Version-3/frontend
```

### Step 2: Install Dependencies

```bash
npm install
```

[Insert Screenshot: npm Install Complete]

### Step 3: Start the Development Server

```bash
ng serve
```

Or alternatively:

```bash
npm start
```

The frontend will be available at `http://localhost:4200`

[Insert Screenshot: Angular Application Running]

### Step 4: Verify Frontend Installation

Open a web browser and navigate to `http://localhost:4200`. You should see the ECommerce Platform homepage.

[Insert Screenshot: Homepage Display]

## 4.4 Database Configuration

The application uses H2 in-memory database by default. Configuration is located in `application.properties`:

```properties
# Database Configuration
spring.datasource.url=jdbc:h2:mem:ecommerce-db
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=password

# H2 Console
spring.h2.console.enabled=true
spring.h2.console.path=/h2-console

# JPA Configuration
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=false
```

### Accessing H2 Console

1. Navigate to `http://localhost:8080/h2-console`
2. Enter JDBC URL: `jdbc:h2:mem:ecommerce-db`
3. Username: `sa`
4. Password: `password`
5. Click **Connect**

[Insert Screenshot: H2 Console Login]

---

# 5. APPLICATION WORKFLOW

## 5.1 Customer Journey

```
[Registration] --> [Browse Products] --> [Add to Cart] --> [Checkout]
                          |                    |               |
                          v                    v               v
                   [View Details]      [Apply Coupon]   [Place Order]
                          |                                    |
                          v                                    v
                   [Add to Wishlist]                   [Track Order]
                          |                                    |
                          v                                    v
                   [Write Review]                    [Request Return]
```

## 5.2 Seller Journey

```
[Registration] --> [Seller Verification] --> [Add Products]
                                                    |
                                                    v
                                            [Manage Inventory]
                                                    |
                                                    v
                                            [Process Orders]
                                                    |
                                                    v
                                            [Track Payouts]
```

## 5.3 Administrator Journey

```
[Login] --> [View Analytics] --> [Manage Users]
                  |                    |
                  v                    v
           [Manage Categories]  [Verify Sellers]
                  |                    |
                  v                    v
           [Create Coupons]    [Process Payouts]
                  |                    |
                  v                    v
           [Configure Zones]   [Handle Orders]
```

---

# 6. MODULE INSTRUCTIONS

## 6.1 Authentication Module

### 6.1.1 User Registration

**Steps to Register:**

1. Navigate to the homepage at `http://localhost:4200`
2. Click the **Register** button in the header navigation
3. Fill in the registration form:
   - *Full Name*: Enter your complete name
   - *Email Address*: Enter a valid email address
   - *Password*: Enter a strong password (minimum 8 characters)
   - *Confirm Password*: Re-enter your password
   - *Phone Number*: Enter your contact number
4. Select your role:
   - **Customer**: For shopping on the platform
   - **Seller**: For selling products (requires verification)
5. Click **Create Account**
6. You will receive a confirmation message upon successful registration

[Insert Screenshot: Registration Form]

### 6.1.2 User Login

**Steps to Login:**

1. Click the **Login** button in the header navigation
2. Enter your registered *Email Address*
3. Enter your *Password*
4. Click **Sign In**
5. Upon successful login, you will be redirected to the appropriate dashboard based on your role

[Insert Screenshot: Login Form]

### 6.1.3 Password Recovery

**Steps to Recover Password:**

1. On the login page, click **Forgot Password?**
2. Enter your registered email address
3. Click **Send Reset Link**
4. Check your email for the password reset link
5. Click the link and enter a new password
6. Confirm the new password and click **Reset Password**

[Insert Screenshot: Password Recovery Form]

## 6.2 Product Catalog Module

### 6.2.1 Browsing Products

**Steps to Browse Products:**

1. From the homepage, click **Shop** or **Products** in the navigation
2. View the product grid displaying available items
3. Use the sidebar filters to narrow down results:
   - *Category*: Select a product category
   - *Price Range*: Set minimum and maximum prices
   - *Rating*: Filter by minimum rating
   - *Availability*: Show only in-stock items
4. Use the **Sort By** dropdown to order results:
   - Price: Low to High
   - Price: High to Low
   - Rating: Highest First
   - Newest First

[Insert Screenshot: Product Listing Page]

### 6.2.2 Searching Products

**Steps to Search:**

1. Locate the search bar at the top of the page
2. Enter your search keywords (e.g., "wireless headphones")
3. Press **Enter** or click the search icon
4. View search results matching your query
5. Use filters to further refine results

[Insert Screenshot: Search Results Page]

### 6.2.3 Viewing Product Details

**Steps to View Product Details:**

1. Click on any product card in the listing
2. View the product detail page showing:
   - Product images
   - Product name and description
   - Current price and any discounts
   - Availability status
   - Seller information
   - Product specifications
   - Customer reviews and ratings
3. Select product variants if available (size, color, etc.)
4. Choose quantity using the +/- buttons

[Insert Screenshot: Product Detail Page]

### 6.2.4 Comparing Products

**Steps to Compare Products:**

1. While browsing products, click the **Compare** icon on product cards
2. Select 2-4 products to compare
3. Click **Compare Selected** button
4. View the comparison table showing:
   - Product images side by side
   - Prices
   - Specifications
   - Ratings
   - Key differences highlighted
5. Click **Add to Cart** on the preferred product

[Insert Screenshot: Product Comparison Page]

## 6.3 Shopping Cart Module

### 6.3.1 Adding Items to Cart

**Steps to Add to Cart:**

1. Navigate to the desired product
2. Select quantity and any variants
3. Click the **Add to Cart** button
4. A confirmation notification will appear
5. The cart icon in the header will update with the item count

[Insert Screenshot: Add to Cart Confirmation]

### 6.3.2 Viewing Cart

**Steps to View Cart:**

1. Click the **Cart** icon in the header navigation
2. View all items currently in your cart
3. For each item, see:
   - Product image and name
   - Selected variants
   - Unit price
   - Quantity
   - Subtotal

[Insert Screenshot: Shopping Cart Page]

### 6.3.3 Updating Cart Items

**Steps to Update Quantity:**

1. In the cart page, locate the item to update
2. Use the **+** button to increase quantity
3. Use the **-** button to decrease quantity
4. The subtotal and cart total will update automatically

**Steps to Remove Item:**

1. Click the **Remove** or trash icon next to the item
2. Confirm removal when prompted
3. The item will be removed from your cart

[Insert Screenshot: Cart Item Update]

### 6.3.4 Applying Coupon Codes

**Steps to Apply Coupon:**

1. In the cart page, locate the coupon section
2. Enter your coupon code in the input field
3. Click **Apply Coupon**
4. If valid, the discount will be applied to your total
5. The new total will display with the discount shown

[Insert Screenshot: Coupon Applied Successfully]

## 6.4 Checkout and Orders Module

### 6.4.1 Checkout Process

**Step 1: Review Cart**

1. Click **Proceed to Checkout** from the cart page
2. Review all items in your order
3. Verify quantities and prices

[Insert Screenshot: Checkout Step 1]

**Step 2: Select Delivery Address**

1. Choose from saved addresses or add a new one
2. To add a new address:
   - Click **Add New Address**
   - Fill in address details:
     - *Full Name*
     - *Phone Number*
     - *Street Address*
     - *City*
     - *State/Province*
     - *Postal Code*
     - *Country*
   - Click **Save Address**
3. Select the address for delivery

[Insert Screenshot: Checkout Step 2]

**Step 3: Select Delivery Options**

1. Choose delivery speed:
   - Standard Delivery (3-5 business days)
   - Priority Delivery (1-2 business days) - Premium members only
2. Select preferred delivery date if available
3. Add delivery instructions if needed

[Insert Screenshot: Checkout Step 3]

**Step 4: Payment**

1. Select payment method:
   - Cash on Delivery (COD)
   - Credit/Debit Card
   - Digital Wallet
2. For card payments, enter:
   - *Card Number*
   - *Expiry Date*
   - *CVV*
   - *Cardholder Name*
3. Review order total including:
   - Subtotal
   - Delivery charges
   - Discount (if coupon applied)
   - Tax
   - **Grand Total**
4. Click **Place Order**

[Insert Screenshot: Checkout Step 4]

**Step 5: Order Confirmation**

1. View order confirmation page
2. Note your Order ID for tracking
3. Receive confirmation email with order details

[Insert Screenshot: Order Confirmation]

### 6.4.2 Order Tracking

**Steps to Track Order:**

1. Navigate to **My Orders** from your profile menu
2. Find the order you want to track
3. Click **Track Order**
4. View order status timeline:
   - Order Placed
   - Order Confirmed
   - Shipped
   - Out for Delivery
   - Delivered
5. View estimated delivery date and carrier information

[Insert Screenshot: Order Tracking Page]

### 6.4.3 Order Cancellation

**Steps to Cancel Order:**

1. Go to **My Orders**
2. Select the order to cancel
3. Click **Cancel Order** (only available before shipping)
4. Select cancellation reason:
   - Changed my mind
   - Found better price elsewhere
   - Ordered by mistake
   - Delivery time too long
   - Other
5. Confirm cancellation
6. Refund will be initiated to original payment method

[Insert Screenshot: Order Cancellation]

### 6.4.4 Return Requests

**Steps to Request Return:**

1. Go to **My Orders**
2. Select the delivered order
3. Click **Request Return**
4. Select items to return
5. Choose return reason:
   - Defective product
   - Wrong item received
   - Product not as described
   - Quality not satisfactory
   - Other
6. Upload photos if applicable
7. Submit return request
8. Wait for seller/admin approval
9. Once approved, schedule pickup or drop-off

[Insert Screenshot: Return Request Form]

## 6.5 Wishlist Module

### 6.5.1 Adding to Wishlist

**Steps to Add to Wishlist:**

1. Navigate to any product
2. Click the **Heart** icon or **Add to Wishlist** button
3. The product will be saved to your wishlist
4. A confirmation notification will appear

[Insert Screenshot: Add to Wishlist]

### 6.5.2 Managing Wishlist

**Steps to View Wishlist:**

1. Click **Wishlist** in the header or profile menu
2. View all saved products
3. For each item, see:
   - Product image and name
   - Current price
   - Availability status

**Steps to Remove from Wishlist:**

1. In the wishlist page, find the item
2. Click the **Remove** icon
3. Confirm removal

**Steps to Move to Cart:**

1. Click **Add to Cart** on any wishlist item
2. The item will be added to your shopping cart
3. Optionally remove from wishlist after adding to cart

[Insert Screenshot: Wishlist Management]

## 6.6 Reviews Module

### 6.6.1 Writing a Review

**Prerequisites:**
- Must have purchased the product
- Order must be delivered

**Steps to Write Review:**

1. Go to **My Orders**
2. Find the delivered order
3. Click **Write Review** next to the product
4. Rate the product (1-5 stars)
5. Enter your review:
   - *Review Title*: Brief summary
   - *Review Body*: Detailed feedback
6. Upload photos (optional)
7. Click **Submit Review**

[Insert Screenshot: Write Review Form]

### 6.6.2 Viewing Reviews

**Steps to View Reviews:**

1. Navigate to any product detail page
2. Scroll to the Reviews section
3. View:
   - Overall rating
   - Rating breakdown (5-star, 4-star, etc.)
   - Individual reviews with:
     - Reviewer name
     - Rating
     - Date
     - Review text
     - Photos (if any)
     - Helpful votes

[Insert Screenshot: Product Reviews Section]

## 6.7 User Profile Module

### 6.7.1 Viewing Profile

**Steps to View Profile:**

1. Click your name/avatar in the header
2. Select **My Profile** from the dropdown
3. View your profile information:
   - Name
   - Email
   - Phone number
   - Account type
   - Premium status
   - Account creation date

[Insert Screenshot: User Profile Page]

### 6.7.2 Editing Profile

**Steps to Edit Profile:**

1. On the profile page, click **Edit Profile**
2. Update desired fields:
   - *Full Name*
   - *Phone Number*
   - *Profile Picture*
3. Click **Save Changes**
4. Confirmation message will appear

[Insert Screenshot: Edit Profile Form]

### 6.7.3 Managing Addresses

**Steps to Add Address:**

1. Go to **My Profile** > **Addresses**
2. Click **Add New Address**
3. Fill in the address form
4. Mark as default if desired
5. Click **Save Address**

**Steps to Edit/Delete Address:**

1. Find the address in your list
2. Click **Edit** to modify or **Delete** to remove
3. Confirm changes

[Insert Screenshot: Address Management]

### 6.7.4 Requesting Seller Role

**Steps to Become a Seller:**

1. Go to **My Profile**
2. Click **Request Seller Account**
3. Fill in business information:
   - *Business Name*
   - *Business Type*
   - *Tax ID/GST Number*
   - *Bank Account Details*
4. Upload required documents:
   - Business registration certificate
   - ID proof
5. Accept seller terms and conditions
6. Submit request
7. Wait for admin verification (typically 2-3 business days)

[Insert Screenshot: Seller Request Form]

## 6.8 Seller Dashboard Module

### 6.8.1 Accessing Seller Dashboard

**Steps:**

1. Login with your seller account
2. You will be redirected to the Seller Dashboard
3. Alternatively, click **Seller Dashboard** in the navigation

[Insert Screenshot: Seller Dashboard Home]

### 6.8.2 Dashboard Overview

The Seller Dashboard displays:
- **Sales Summary**: Total sales, revenue, orders
- **Recent Orders**: Latest orders requiring attention
- **Top Products**: Best-selling items
- **Performance Metrics**: Conversion rates, ratings
- **Payout Balance**: Pending and available balance

[Insert Screenshot: Dashboard Metrics]

### 6.8.3 Adding Products

**Steps to Add Product:**

1. Navigate to **Products** > **Add New Product**
2. Enter basic information:
   - *Product Name*
   - *Description*
   - *SKU*
   - *Category* (select from dropdown)
3. Enter pricing information:
   - *Regular Price*
   - *Sale Price* (optional)
   - *Stock Quantity*
4. Upload product images:
   - Main image (required)
   - Additional images (up to 5)
5. Enter specifications:
   - Add key-value pairs for product specs
6. Set availability:
   - *Status*: Active/Draft
   - *Visibility*: Public/Private
7. Click **Save Product**

[Insert Screenshot: Add Product Form]

### 6.8.4 Managing Inventory

**Steps to Update Stock:**

1. Go to **Products** > **All Products**
2. Find the product to update
3. Click **Edit** or the stock quantity field
4. Enter new stock quantity
5. Save changes

**Bulk Stock Update:**

1. Go to **Products** > **Inventory**
2. Select multiple products
3. Click **Bulk Update**
4. Enter stock adjustments
5. Apply changes

[Insert Screenshot: Inventory Management]

### 6.8.5 Managing Orders

**Steps to Process Order:**

1. Go to **Orders** in the seller menu
2. View pending orders
3. Click on an order to view details
4. Update order status:
   - Confirm Order
   - Mark as Shipped (enter tracking number)
   - Mark as Delivered
5. Handle return requests:
   - View return reason
   - Approve or reject return
   - Process refund if applicable

[Insert Screenshot: Seller Order Management]

### 6.8.6 Viewing Payouts

**Steps to View Payouts:**

1. Go to **Payouts** in the seller menu
2. View payout summary:
   - Total earnings
   - Pending amount
   - Available for withdrawal
   - Commission deducted
3. View payout history
4. Request payout:
   - Click **Request Payout**
   - Enter amount
   - Confirm bank details
   - Submit request
   - Wait for admin approval

[Insert Screenshot: Seller Payouts]

## 6.9 Admin Dashboard Module

### 6.9.1 Accessing Admin Dashboard

**Steps:**

1. Login with admin credentials
2. You will be redirected to the Admin Dashboard
3. View platform-wide statistics and controls

[Insert Screenshot: Admin Dashboard Home]

### 6.9.2 Analytics Overview

The Admin Dashboard displays:
- **Total Users**: Registered customers and sellers
- **Total Orders**: All-time and monthly orders
- **Revenue**: Gross and net revenue figures
- **Active Products**: Total listed products
- **Pending Verifications**: Sellers awaiting verification
- **Charts**: Sales trends, user growth, category performance

[Insert Screenshot: Admin Analytics]

### 6.9.3 User Management

**Steps to View Users:**

1. Go to **Users** in the admin menu
2. View user list with filters:
   - Role (Customer/Seller/Admin)
   - Status (Active/Inactive)
   - Registration date

**Steps to Manage User:**

1. Click on a user to view details
2. Available actions:
   - Update role
   - Verify seller
   - Deactivate account
   - Delete account (with confirmation)

[Insert Screenshot: Admin User Management]

### 6.9.4 Category Management

**Steps to Add Category:**

1. Go to **Categories** in the admin menu
2. Click **Add Category**
3. Enter:
   - *Category Name*
   - *Description*
   - *Parent Category* (for subcategories)
   - *Category Image*
4. Click **Save Category**

**Steps to Edit/Delete Category:**

1. Find the category in the list
2. Click **Edit** to modify or **Delete** to remove
3. Confirm changes

[Insert Screenshot: Category Management]

### 6.9.5 Coupon Management

**Steps to Create Coupon:**

1. Go to **Coupons** in the admin menu
2. Click **Create Coupon**
3. Enter coupon details:
   - *Coupon Code*
   - *Discount Type*: Percentage or Fixed Amount
   - *Discount Value*
   - *Minimum Order Amount*
   - *Maximum Discount* (for percentage coupons)
   - *Valid From* and *Valid Until* dates
   - *Usage Limit* (total uses allowed)
   - *Usage Per User* (uses per customer)
4. Set conditions:
   - *Categories*: Apply to specific categories
   - *Products*: Apply to specific products
   - *User Types*: All users or premium only
5. Click **Create Coupon**

[Insert Screenshot: Create Coupon Form]

### 6.9.6 Delivery Zone Management

**Steps to Configure Delivery Zones:**

1. Go to **Delivery Zones** in the admin menu
2. Click **Add Zone**
3. Enter zone details:
   - *Zone Name*
   - *Postal Codes* covered
   - *Delivery Charge*
   - *Minimum Order for Free Delivery*
   - *Estimated Delivery Days*
4. Save zone configuration

[Insert Screenshot: Delivery Zone Configuration]

### 6.9.7 Order Administration

**Steps to Manage Orders:**

1. Go to **Orders** in the admin menu
2. View all platform orders
3. Filter by:
   - Status
   - Date range
   - Seller
   - Customer
4. Click on order to view details
5. Take actions:
   - Update status
   - Process refund
   - Contact customer/seller

[Insert Screenshot: Admin Order Management]

### 6.9.8 Payout Administration

**Steps to Process Payouts:**

1. Go to **Payouts** in the admin menu
2. View pending payout requests
3. Click on a request to review:
   - Seller details
   - Order breakdown
   - Commission calculation
4. Actions:
   - **Approve**: Process the payout
   - **Reject**: Decline with reason
5. View payout history

[Insert Screenshot: Admin Payout Processing]

### 6.9.9 Subscription Management

**Steps to Manage Subscriptions:**

1. Go to **Subscriptions** in the admin menu
2. View all premium subscriptions
3. Actions available:
   - View subscription details
   - Extend subscription
   - Cancel subscription
   - Issue refund

[Insert Screenshot: Subscription Management]

## 6.10 Premium Subscription Module

### 6.10.1 Subscription Plans

The platform offers two premium subscription plans:

| Feature | Monthly Plan | Yearly Plan |
|---------|--------------|-------------|
| Price | $9.99/month | $99.99/year |
| Priority Delivery | Yes | Yes |
| Early Access | Yes | Yes |
| Exclusive Deals | Yes | Yes |
| Free Delivery | Orders > $25 | All orders |
| Savings | - | Save $19.89 |

### 6.10.2 Subscribing to Premium

**Steps to Subscribe:**

1. Go to **My Profile** > **Premium Subscription**
2. View subscription plans and benefits
3. Select desired plan (Monthly or Yearly)
4. Click **Subscribe Now**
5. Enter payment details
6. Confirm subscription
7. Premium benefits activate immediately

[Insert Screenshot: Premium Subscription Page]

### 6.10.3 Managing Subscription

**Steps to Manage:**

1. Go to **My Profile** > **Premium Subscription**
2. View current subscription status:
   - Plan type
   - Renewal date
   - Payment history
3. Available actions:
   - **Change Plan**: Switch between monthly/yearly
   - **Cancel Subscription**: End auto-renewal
   - **Update Payment**: Change payment method

[Insert Screenshot: Manage Subscription]

---

# 7. TROUBLESHOOTING

## 7.1 Common Issues and Solutions

### Issue: Cannot Login

**Symptoms:**
- Login button not responding
- "Invalid credentials" error
- Page stuck loading

**Solutions:**
1. Verify email and password are correct
2. Check if Caps Lock is enabled
3. Clear browser cache and cookies
4. Try using incognito/private browsing mode
5. Reset password if forgotten
6. Contact support if issue persists

### Issue: Products Not Loading

**Symptoms:**
- Empty product list
- Loading spinner never stops
- Error message displayed

**Solutions:**
1. Check internet connection
2. Refresh the page
3. Clear browser cache
4. Verify backend server is running
5. Check browser console for errors

### Issue: Add to Cart Not Working

**Symptoms:**
- "Add to Cart" button unresponsive
- Error when adding items
- Cart count not updating

**Solutions:**
1. Ensure you are logged in
2. Check product availability (in stock)
3. Clear browser cache
4. Try a different browser
5. Check for JavaScript errors

### Issue: Payment Failing

**Symptoms:**
- Payment not processing
- "Payment failed" error
- Transaction timeout

**Solutions:**
1. Verify card details are correct
2. Check sufficient balance/credit limit
3. Contact your bank for any blocks
4. Try alternative payment method
5. Contact support with transaction ID

### Issue: Order Not Appearing

**Symptoms:**
- Order confirmation received but not visible
- "No orders" shown in My Orders

**Solutions:**
1. Refresh the page
2. Check spam folder for confirmation email
3. Wait a few minutes and retry
4. Contact support with confirmation details

## 7.2 Error Messages

| Error Code | Message | Solution |
|------------|---------|----------|
| ERR-001 | Session expired | Login again |
| ERR-002 | Product not found | Product may have been removed |
| ERR-003 | Insufficient stock | Reduce quantity or wait for restock |
| ERR-004 | Invalid coupon | Check code and validity period |
| ERR-005 | Payment declined | Try different payment method |
| ERR-006 | Address not serviceable | Choose different delivery address |

## 7.3 Performance Issues

**Slow Page Loading:**
1. Check internet speed
2. Close unnecessary browser tabs
3. Disable browser extensions
4. Try different browser
5. Clear browser cache

**Images Not Loading:**
1. Check internet connection
2. Disable ad blockers
3. Clear browser cache
4. Refresh the page

---

# 8. FREQUENTLY ASKED QUESTIONS (FAQs)

## 8.1 Account Related

**Q: How do I create an account?**
A: Click the "Register" button in the header, fill in your details, and submit the registration form. You will receive a confirmation email.

**Q: Can I change my email address?**
A: Currently, email addresses cannot be changed after registration. Contact support for assistance.

**Q: How do I upgrade from Customer to Seller?**
A: Go to My Profile and click "Request Seller Account." Fill in the required business information and submit for verification.

**Q: What happens if I forget my password?**
A: Click "Forgot Password" on the login page, enter your email, and follow the reset link sent to your inbox.

## 8.2 Shopping Related

**Q: How can I find products?**
A: Use the search bar to search by keywords, or browse by category. You can also use filters to narrow down results.

**Q: Can I save products for later?**
A: Yes, add products to your Wishlist by clicking the heart icon. View your wishlist anytime from the profile menu.

**Q: How do I apply a coupon code?**
A: In the cart page, enter your coupon code in the designated field and click "Apply." The discount will be reflected in your total.

**Q: Can I compare products?**
A: Yes, click the compare icon on product cards to add them to comparison. Compare up to 4 products side by side.

## 8.3 Order Related

**Q: How can I track my order?**
A: Go to My Orders, find your order, and click "Track Order" to see the current status and delivery updates.

**Q: Can I cancel my order?**
A: Orders can be cancelled before they are shipped. Go to My Orders and click "Cancel Order" on the relevant order.

**Q: What is the return policy?**
A: Most products can be returned within 7 days of delivery. Go to My Orders and click "Request Return" to initiate.

**Q: How long does delivery take?**
A: Standard delivery takes 3-5 business days. Premium members can opt for priority delivery (1-2 business days).

## 8.4 Payment Related

**Q: What payment methods are accepted?**
A: We accept Cash on Delivery (COD), Credit/Debit Cards, and Digital Wallets.

**Q: Is my payment information secure?**
A: Yes, all payment transactions are encrypted using industry-standard SSL/TLS protocols.

**Q: When will I receive my refund?**
A: Refunds are processed within 5-7 business days after approval. Bank processing may take additional time.

## 8.5 Seller Related

**Q: How long does seller verification take?**
A: Seller verification typically takes 2-3 business days after submitting all required documents.

**Q: How is commission calculated?**
A: Commission rates vary by category, typically ranging from 5-15% of the sale price.

**Q: When do I receive my payouts?**
A: Payouts are processed weekly for orders that are delivered and past the return period.

## 8.6 Premium Subscription

**Q: What are the benefits of Premium?**
A: Premium members get priority delivery, early access to sales, exclusive deals, and free delivery on eligible orders.

**Q: Can I cancel my subscription?**
A: Yes, you can cancel anytime from My Profile > Premium Subscription. Benefits continue until the end of the billing period.

**Q: Will I be charged automatically?**
A: Yes, subscriptions auto-renew unless cancelled before the renewal date.

---

# 9. GLOSSARY

| Term | Definition |
|------|------------|
| **Add to Cart** | Action of placing a product in the shopping cart for purchase |
| **API** | Application Programming Interface - Method for software components to communicate |
| **Backend** | Server-side application that processes business logic and data |
| **Cart** | Virtual shopping container holding items selected for purchase |
| **Category** | Classification system for organizing products |
| **Checkout** | Process of completing a purchase by providing delivery and payment information |
| **Coupon** | Promotional code providing a discount on purchases |
| **CRUD** | Create, Read, Update, Delete - Basic data operations |
| **Customer** | User role for individuals purchasing products |
| **Delivery Zone** | Geographic area where delivery services are available |
| **DTO** | Data Transfer Object - Object for transferring data between layers |
| **Frontend** | Client-side application providing user interface |
| **H2 Database** | In-memory database used for development and testing |
| **JPA** | Java Persistence API - Specification for object-relational mapping |
| **ORM** | Object-Relational Mapping - Technique for database interaction |
| **Payout** | Transfer of earned funds from platform to seller |
| **Premium** | Subscription service providing enhanced features |
| **REST API** | Representational State Transfer API - Web service architecture |
| **Review** | Customer feedback and rating for a product |
| **Seller** | User role for merchants listing and selling products |
| **SKU** | Stock Keeping Unit - Unique product identifier |
| **Spring Boot** | Java framework for building backend applications |
| **Swagger** | API documentation and testing tool |
| **Wishlist** | Collection of products saved for future consideration |

---

# 10. APPENDIX

## Appendix A: Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| Ctrl/Cmd + K | Open search |
| Esc | Close modal/dropdown |
| Enter | Submit form |
| Tab | Navigate between fields |

## Appendix B: Supported Browsers

| Browser | Minimum Version |
|---------|-----------------|
| Google Chrome | 90+ |
| Mozilla Firefox | 88+ |
| Apple Safari | 14+ |
| Microsoft Edge | 90+ |

## Appendix C: API Endpoints Reference

### Authentication
- POST `/auth/register` - Register new user
- POST `/auth/login` - User login

### Products
- GET `/products` - List products
- GET `/products/{id}` - Get product details
- POST `/products/search` - Search products
- POST `/products/compare` - Compare products

### Cart
- GET `/user/cart` - View cart
- POST `/user/cart/add` - Add to cart
- PUT `/user/cart/{id}` - Update item
- DELETE `/user/cart/{id}` - Remove item

### Orders
- POST `/user/orders` - Place order
- GET `/user/orders` - List orders
- GET `/user/orders/{id}` - Order details
- POST `/user/orders/{id}/cancel` - Cancel order

## Appendix D: Contact Information

**Technical Support**
- Email: support@ecommerce-platform.com
- Phone: +1-800-SUPPORT
- Hours: Monday-Friday, 9:00 AM - 6:00 PM EST

**Sales Inquiries**
- Email: sales@ecommerce-platform.com
- Phone: +1-800-SALES01

**Report Issues**
- GitHub: https://github.com/organization/ecommerce-platform/issues

## Appendix E: Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | January 2026 | Initial release |
| 2.0 | March 2026 | Added seller features |
| 3.0 | January 2026 | Premium subscription, enhanced admin |

---

**End of User Manual**

*Document generated on January 30, 2026*
*ECommerce Platform Version 3.0*
