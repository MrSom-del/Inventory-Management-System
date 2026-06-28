# 📦 Inventory Management System

A modern, full-stack inventory management application built with **Spring Boot** and **React**. Manage your products, track orders, and monitor inventory levels with an intuitive, professional UI.

![GitHub](https://img.shields.io/github/license/your-username/Inventory)
![Java](https://img.shields.io/badge/Java-21-orange)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.3.4-brightgreen)
![React](https://img.shields.io/badge/React-19.2-blue)
![MySQL](https://img.shields.io/badge/MySQL-Database-blue)

## ✨ Features

### 📊 Dashboard
- **Real-time Statistics**: View total products, low stock items, out-of-stock count, and total inventory value
- **Recent Orders**: Track the last 5 orders with status and details
- **Quick Actions**: Fast access to product management and order creation

### 📦 Product Management
- ✏️ Create, read, update, and delete products
- 🎯 Real-time search and filtering
- 📊 Sortable columns (name, category, price, quantity)
- 🎨 **Visual Stock Status Indicators**:
  - 🟢 **Green**: High stock (> 50 units)
  - 🔵 **Blue**: Normal stock (6-50 units)
  - 🟠 **Orange**: Low stock (1-5 units)
  - 🔴 **Red**: Out of stock (0 units)
- 📈 Progress bars showing inventory levels
- 📄 Flexible pagination (5, 10, 25, 50 items per page)

### 🧾 Order Management
- 🛒 Create and manage orders
- 🔄 Track order status (New, Paid, Cancelled, Delivered)
- 📋 View detailed order information with items breakdown
- 💰 Real-time total calculation
- 📱 Responsive order details view

### 🎨 Modern UI/UX
- **Professional Dark Sidebar** with intuitive navigation
- **Responsive Design**: Works seamlessly on mobile, tablet, and desktop
- **Color-Coded System**: Visual indicators for quick status recognition
- **Smooth Animations**: Elegant transitions and hover effects
- **Toast Notifications**: Success and error messages
- **Gradient Effects**: Modern visual enhancements

## 🛠️ Tech Stack

### Backend
- **Framework**: Spring Boot 3.3.4
- **Language**: Java 21
- **Database**: MySQL 8.0
- **ORM**: Spring Data JPA / Hibernate
- **API**: RESTful API

### Frontend
- **Framework**: React 19.2.0
- **Styling**: Tailwind CSS 3.4
- **HTTP Client**: Axios
- **Routing**: React Router DOM
- **Build Tool**: Create React App

## 📋 Prerequisites

Before you begin, ensure you have installed:

- **Java 21+**: [Download](https://www.oracle.com/java/technologies/downloads/#java21)
- **Node.js 16+**: [Download](https://nodejs.org/)
- **MySQL 8.0+**: [Download](https://dev.mysql.com/downloads/mysql/)
- **Maven 3.6+**: Usually comes with Java

## 🚀 Quick Start

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/Inventory.git
cd Inventory
```

### 2. Database Setup
Create a MySQL database named `inventory_db`:
```sql
CREATE DATABASE inventory_db;
USE inventory_db;
```

Update the database credentials in `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/inventory_db?useSSL=false&serverTimezone=UTC
spring.datasource.username=your_mysql_username
spring.datasource.password=your_mysql_password
```

### 3. Backend Setup & Run
```bash
# Navigate to project root
cd /path/to/Inventory

# Build the project
mvn clean install

# Run the backend server
mvn spring-boot:run
```
The backend will start on `http://localhost:8080`

### 4. Frontend Setup & Run
In a new terminal:
```bash
# Navigate to frontend directory
cd inventory-frontend

# Install dependencies
npm install

# Start the development server
npm start
```
The frontend will open at `http://localhost:3000`

## 📚 Project Structure

```
Inventory/
├── src/
│   └── main/
│       ├── java/com/example/inventory/
│       │   ├── InventoryApplication.java       # Main Spring Boot app
│       │   ├── controller/                       # REST API endpoints
│       │   │   ├── DashboardController.java
│       │   │   ├── ProductController.java
│       │   │   └── OrderController.java
│       │   ├── model/                            # Entity classes
│       │   │   ├── Product.java
│       │   │   ├── Order.java
│       │   │   ├── OrderItem.java
│       │   │   └── OrderStatus.java
│       │   ├── repository/                       # Data access layer
│       │   │   ├── ProductRepository.java
│       │   │   ├── OrderRepository.java
│       │   │   └── OrderItemRepository.java
│       │   └── dto/                              # Data transfer objects
│       │       └── CreateOrderRequest.java
│       └── resources/
│           └── application.properties            # Configuration
│
├── inventory-frontend/
│   ├── public/                                   # Static assets
│   ├── src/
│   │   ├── components/                           # React components
│   │   │   ├── Layout.jsx
│   │   │   ├── Sidebar.jsx
│   │   │   ├── Topbar.jsx
│   │   │   ├── StatCard.jsx
│   │   │   ├── ProductModal.jsx
│   │   │   ├── AddOrderModal.jsx
│   │   │   └── Toast.jsx
│   │   ├── pages/                                # Page components
│   │   │   ├── Dashboard.jsx
│   │   │   ├── Products.jsx
│   │   │   ├── Orders.jsx
│   │   │   └── OrderDetails.jsx
│   │   ├── services/                             # API services
│   │   │   ├── api.js
│   │   │   ├── DashboardService.js
│   │   │   ├── ProductService.js
│   │   │   └── OrderService.js
│   │   ├── App.js
│   │   └── index.js
│   └── package.json
│
└── pom.xml                                       # Maven configuration
```

## 🔌 API Endpoints

### Dashboard
```
GET /api/dashboard/stats              # Get dashboard statistics
```

### Products
```
GET    /api/products                  # Get all products
POST   /api/products                  # Create new product
GET    /api/products/{id}             # Get product by ID
PUT    /api/products/{id}             # Update product
DELETE /api/products/{id}             # Delete product
```

### Orders
```
GET    /api/orders                    # Get all orders
POST   /api/orders                    # Create new order
GET    /api/orders/{id}               # Get order details
PUT    /api/orders/{id}/status        # Update order status
DELETE /api/orders/{id}               # Delete order
```

## 🎨 Color & Status System

### Stock Status Colors
| Status | Color | Range |
|--------|-------|-------|
| High Stock | 🟢 Green | > 50 units |
| Normal Stock | 🔵 Blue | 6-50 units |
| Low Stock | 🟠 Orange | 1-5 units |
| Out of Stock | 🔴 Red | 0 units |

### Order Status Colors
| Status | Color | Meaning |
|--------|-------|---------|
| New | 🔵 Blue | Order just created |
| Paid | 🟢 Green | Payment processed |
| Cancelled | ❌ Red | Order cancelled |
| Delivered | 🟣 Purple | Delivered |

## 💾 Database Schema

### Products Table
```sql
CREATE TABLE product (
  id BIGINT PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(255) NOT NULL,
  category VARCHAR(100),
  price DECIMAL(10, 2) NOT NULL,
  quantity INT DEFAULT 0,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Orders Table
```sql
CREATE TABLE orders (
  id BIGINT PRIMARY KEY AUTO_INCREMENT,
  customer_name VARCHAR(255),
  status VARCHAR(50) DEFAULT 'NEW',
  total_amount DECIMAL(10, 2),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### OrderItems Table
```sql
CREATE TABLE order_item (
  id BIGINT PRIMARY KEY AUTO_INCREMENT,
  order_id BIGINT NOT NULL,
  product_id BIGINT NOT NULL,
  quantity INT NOT NULL,
  price DECIMAL(10, 2) NOT NULL,
  FOREIGN KEY (order_id) REFERENCES orders(id),
  FOREIGN KEY (product_id) REFERENCES product(id)
);
```

## 🧪 Testing

### Backend Tests
```bash
# Run all tests
mvn test

# Run specific test
mvn test -Dtest=TestClassName
```

### Frontend Tests
```bash
# Run all tests
npm test

# Run with coverage
npm test -- --coverage
```

## 🐛 Troubleshooting

### Backend won't start
- Ensure MySQL is running
- Check database credentials in `application.properties`
- Verify Java 21 is installed: `java -version`
- Check Maven is installed: `mvn -version`

### Frontend shows old design
- Hard refresh: `Ctrl+Shift+R` (Windows) or `Cmd+Shift+R` (Mac)
- Clear browser cache
- Delete `node_modules` and reinstall: `npm install`

### API requests failing
- Ensure backend is running on port 8080
- Check CORS configuration in backend
- Verify database connection

### Styling not appearing
- Make sure Tailwind CSS is installed: `npm install`
- Restart frontend: `npm start`
- Check console for CSS warnings

## 📈 Performance Optimization

- **Pagination**: Load only needed data per page
- **Lazy Loading**: Components load on demand
- **Caching**: Smart client-side caching
- **Database Indexing**: Optimized queries
- **Code Splitting**: React lazy loading for routes

## 🔒 Security Considerations

- Input validation on both backend and frontend
- SQL injection prevention with parameterized queries
- CORS configuration for API security
- Environment variables for sensitive data (in production)
- Hash passwords if authentication is added

## 📝 Future Enhancements

- [ ] User authentication and authorization
- [ ] Advanced reporting and analytics
- [ ] Export to Excel/PDF functionality
- [ ] Inventory alerts and notifications
- [ ] Multi-language support
- [ ] Dark mode toggle
- [ ] Advanced search filters
- [ ] Order history and archival

---

## 🎉 Screenshots

### Dashboard
Clean overview with stats and recent orders

### Products Page
Search, sort, and manage inventory with visual stock indicators

### Orders Management
Create and track orders with status updates
