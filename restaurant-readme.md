# Restaurant Ordering System

A full-stack web application for restaurant management with online ordering, table booking, and admin dashboard capabilities.

## 🚀 Features

### Customer Features
- **User Authentication** - Register and login functionality
- **Browse Menu** - View complete restaurant menu with categories
- **Shopping Cart** - Add/remove items and manage quantities
- **Online Ordering** - Place orders with real-time updates
- **Table Booking** - Reserve tables for dine-in
- **Order Tracking** - Track order status and history
- **Promotional Offers** - View current deals and discounts

### Admin Features
- **Dashboard** - Overview of orders, bookings, and revenue
- **Menu Management** - Add, edit, and delete food items
- **Order Management** - View and update order status
- **Table Management** - Manage table bookings
- **User Management** - View customer information
- **Bill Generation** - Automatic billing with order details

## 🛠️ Tech Stack

### Frontend
- **Vue.js 3** - Progressive JavaScript framework
- **Vue Router** - Client-side routing
- **Vuex** - State management
- **Axios** - HTTP client for API calls
- **Bootstrap 5** - Responsive UI framework
- **CSS3** - Custom styling

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web application framework
- **MySQL** - Relational database
- **Sequelize** - ORM for MySQL
- **JWT** - JSON Web Tokens for authentication
- **bcrypt** - Password hashing

## 📋 Prerequisites

Before running this project, make sure you have:

- **Node.js** (v14 or higher) - [Download](https://nodejs.org/)
- **MySQL** (v5.7 or higher) - [Download](https://dev.mysql.com/downloads/)
- **npm** or **yarn** - Package manager
- **Git** - Version control

## 🔧 Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/dhanasai2/restaurant_Ordering_system_FST.git
cd restaurant_Ordering_system_FST
```

### 2. Database Setup

1. Start MySQL server
2. Create a new database:

```sql
CREATE DATABASE db_restaurant;
```

3. Import the database schema:

```bash
mysql -u root -p db_restaurant < frontend/src/resources/db_restaurant.sql
```

Or use phpMyAdmin to import the SQL file.

### 3. Backend Setup

```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Configure database connection
# Edit config/database.js with your MySQL credentials:
# - host: localhost
# - user: your_mysql_username
# - password: your_mysql_password
# - database: db_restaurant

# Start backend server
npm start
```

Backend will run on `http://localhost:5000`

### 4. Frontend Setup

```bash
# Navigate to frontend directory (from root)
cd frontend

# Install dependencies
npm install

# Start development server
npm run serve
```

Frontend will run on `http://localhost:8080`

## 🗄️ Database Configuration

Update `backend/config/database.js` with your MySQL credentials:

```javascript
const mysql = require('mysql2');

const connection = mysql.createConnection({
  host: 'localhost',
  user: 'root',           // Your MySQL username
  password: '',           // Your MySQL password
  database: 'db_restaurant'
});

module.exports = connection;
```

## 📁 Project Structure

```
restaurant-ordering-system/
├── backend/
│   ├── config/
│   │   └── database.js          # Database configuration
│   ├── controllers/
│   │   ├── user.js              # User authentication logic
│   │   ├── food.js              # Food menu operations
│   │   ├── cart.js              # Shopping cart management
│   │   ├── booktable.js         # Table booking logic
│   │   ├── billdetails.js       # Billing operations
│   │   └── billstatus.js        # Order status management
│   ├── models/
│   │   ├── UserModel.js         # User schema
│   │   ├── FoodModel.js         # Food item schema
│   │   ├── CartModel.js         # Cart schema
│   │   ├── BookTableModel.js    # Table booking schema
│   │   ├── BillDetailsModel.js  # Bill details schema
│   │   └── BillStatusModel.js   # Order status schema
│   ├── routes/
│   │   └── routes.js            # API endpoints
│   ├── index.js                 # Server entry point
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── admin/
│   │   │   ├── Admin.vue        # Admin layout
│   │   │   └── Dashboard.vue    # Admin dashboard
│   │   ├── components/
│   │   │   ├── NavBar.vue       # Navigation bar
│   │   │   ├── FooterComponent.vue
│   │   │   ├── OrderDetails.vue # Order information
│   │   │   └── QuickView.vue    # Product quick view
│   │   ├── pages/
│   │   │   ├── Home.vue         # Homepage
│   │   │   ├── Menu.vue         # Menu page
│   │   │   ├── Cart.vue         # Shopping cart
│   │   │   ├── Checkout.vue     # Checkout page
│   │   │   ├── Login.vue        # Login page
│   │   │   ├── Register.vue     # Registration page
│   │   │   ├── Table.vue        # Table booking
│   │   │   ├── MyOrder.vue      # Order history
│   │   │   ├── Promo.vue        # Promotions
│   │   │   ├── About.vue        # About page
│   │   │   └── Thank.vue        # Thank you page
│   │   ├── router/
│   │   │   └── index.js         # Route configuration
│   │   ├── store/
│   │   │   └── index.js         # Vuex store
│   │   ├── assets/
│   │   │   └── css/
│   │   │       └── global_style.css
│   │   ├── axios.js             # Axios configuration
│   │   ├── App.vue              # Root component
│   │   └── main.js              # App entry point
│   ├── public/
│   │   └── index.html
│   ├── package.json
│   └── vue.config.js
└── README.md
```

## 🔌 API Endpoints

### Authentication
- `POST /api/register` - User registration
- `POST /api/login` - User login

### Food Menu
- `GET /api/foods` - Get all food items
- `GET /api/food/:id` - Get single food item
- `POST /api/food` - Add new food item (Admin)
- `PUT /api/food/:id` - Update food item (Admin)
- `DELETE /api/food/:id` - Delete food item (Admin)

### Cart
- `GET /api/cart/:userId` - Get user's cart
- `POST /api/cart` - Add item to cart
- `PUT /api/cart/:id` - Update cart item
- `DELETE /api/cart/:id` - Remove from cart

### Orders
- `POST /api/order` - Place order
- `GET /api/orders/:userId` - Get user orders
- `GET /api/orders` - Get all orders (Admin)
- `PUT /api/order/:id` - Update order status (Admin)

### Table Booking
- `POST /api/booktable` - Book a table
- `GET /api/bookings` - Get all bookings (Admin)

## 🚦 Usage

### For Customers

1. **Register/Login** - Create an account or login
2. **Browse Menu** - Explore available food items
3. **Add to Cart** - Select items and quantities
4. **Checkout** - Review order and place it
5. **Track Order** - Monitor order status in "My Orders"
6. **Book Table** - Reserve a table for dine-in

### For Admins

1. **Login** with admin credentials
2. **Dashboard** - View statistics and recent orders
3. **Manage Menu** - Add/edit/delete food items
4. **Process Orders** - Update order status
5. **View Bookings** - Manage table reservations

## 🎨 Default Admin Credentials

```
Email: admin@restaurant.com
Password: admin123
```

**⚠️ Important:** Change these credentials after first login for security!

## 📦 Build for Production

### Backend
```bash
cd backend
npm start
```

### Frontend
```bash
cd frontend
npm run build
```

The production-ready files will be in `frontend/dist/`

## 🔐 Environment Variables

Create a `.env` file in the backend directory:

```env
PORT=5000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=db_restaurant
JWT_SECRET=your_jwt_secret_key
```

## 🐛 Troubleshooting

### Database Connection Issues
- Verify MySQL is running
- Check database credentials in `config/database.js`
- Ensure database `db_restaurant` exists

### Port Already in Use
```bash
# Change port in backend/index.js
const PORT = 5001; // or any available port
```

### CORS Issues
- Backend already configured for CORS
- Check `backend/index.js` for CORS settings

### Module Not Found
```bash
# Reinstall dependencies
npm install
```

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Dhana Sai**
- GitHub: [@dhanasai2](https://github.com/dhanasai2)

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📧 Support

For support, email: dhanasai@example.com or create an issue in the repository.

## 🌟 Acknowledgments

- Vue.js community for excellent documentation
- Express.js for robust backend framework
- Bootstrap team for responsive design components

---

⭐ If you find this project useful, please give it a star on GitHub!
