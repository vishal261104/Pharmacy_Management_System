# 🏥 Pharmacy Management System

A comprehensive full-stack pharmacy management system built with React, Node.js, Express, and MongoDB. This application helps pharmacies manage inventory, sales, purchases, customers, suppliers, and provides an AI-powered chatbot assistant.

## ✨ Features

### Core Functionality
- **Inventory Management**: Track medicines, stock levels, expiry dates, and batch numbers
- **Sales Management**: Process sales transactions with automatic stock updates and invoice generation
- **Purchase Management**: Manage supplier orders and update inventory
- **Customer Management**: Maintain customer records with contact details and purchase history
- **Supplier Management**: Track supplier information and order history
- **Credentials Management**: Secure storage and management of pharmacy credentials

### Advanced Features
- **AI Chatbot**: OpenAI-powered intelligent assistant for medicine information and pharmacy queries
- **Loyalty Points System**: Reward customers with points on purchases and enable redemption
- **Email-Based Login**: Secure authentication system with JWT tokens
- **Password Reset**: Forgot password functionality with email verification
- **Admin Dashboard**: Comprehensive analytics and insights
- **Real-time Stock Alerts**: Notifications for low stock and expiring medicines
- **Invoice Generation**: Automatic invoice creation with QR codes
- **Security Features**: Password hashing, JWT authentication, and role-based access control

## 🛠️ Tech Stack

### Frontend
- **React** 19.0.0 - UI library
- **React Router DOM** - Client-side routing
- **Ant Design** - UI component library
- **Recharts** - Data visualization
- **React Markdown** - Markdown rendering for chatbot
- **QRCode.react** - QR code generation

### Backend
- **Node.js** - Runtime environment
- **Express** - Web application framework
- **MongoDB** with Mongoose - Database
- **JWT** - Authentication
- **Bcrypt** - Password hashing
- **Nodemailer** - Email functionality
- **OpenAI API** - AI chatbot integration
- **Natural** - NLP for chatbot
- **CORS** - Cross-origin resource sharing

## 📋 Prerequisites

Before running this application, make sure you have:
- Node.js (v14 or higher)
- MongoDB (local or Atlas)
- OpenAI API key (for chatbot functionality)
- Email service credentials (for email features)

## 🚀 Installation

### 1. Clone the repository
```bash
git clone https://github.com/vishal261104/Pharmacy_Management_System.git
cd Pharmacy_Management_System
```

### 2. Backend Setup

```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Create .env file
# Copy env.example to .env and fill in your credentials
cp env.example .env
```

Configure your `.env` file:
```env
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
OPENAI_API_KEY=your_openai_api_key
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_email_password
PORT=5000
```

### 3. Frontend Setup

```bash
# Navigate to frontend directory (from root)
cd frontend

# Install dependencies
npm install
```

## 🎯 Usage

### Start Backend Server
```bash
cd backend
node server.js
```
Backend will run on `http://localhost:5000`

### Start Frontend Application
```bash
cd frontend
npm start
```
Frontend will run on `http://localhost:3000`

### Default Admin Credentials
- **Email**: admin@pharmacy.com
- **Password**: admin123

⚠️ **Important**: Change the default admin password after first login!

## 📁 Project Structure

```
Pharmacy_Management_System/
├── backend/
│   ├── config/
│   │   └── db.js                 # Database configuration
│   ├── controllers/              # Request handlers
│   │   ├── chatbotController.js
│   │   ├── credentialController.js
│   │   ├── customerController.js
│   │   ├── productController.js
│   │   ├── purchaseController.js
│   │   ├── salesController.js
│   │   └── supplierController.js
│   ├── middleware/
│   │   └── auth.js               # Authentication middleware
│   ├── models/                   # Database schemas
│   │   ├── customerModel.js
│   │   ├── productModel.js
│   │   ├── purchaseModel.js
│   │   ├── Sales.js
│   │   ├── stockModel.js
│   │   ├── supplierModel.js
│   │   └── User.js
│   ├── routes/                   # API routes
│   │   ├── adminRoutes.js
│   │   ├── auth.js
│   │   ├── chatbotRoutes.js
│   │   ├── customerRoutes.js
│   │   ├── productRoutes.js
│   │   ├── purchaseRoutes.js
│   │   ├── salesRoutes.js
│   │   ├── stockRoutes.js
│   │   ├── supplierRoutes.js
│   │   └── userRoutes.js
│   ├── utils/                    # Utility functions
│   │   ├── emailUtils.js
│   │   ├── jwtUtils.js
│   │   └── passwordUtils.js
│   ├── server.js                 # Entry point
│   └── package.json
│
├── frontend/
│   ├── public/
│   │   ├── index.html
│   │   └── manifest.json
│   ├── src/
│   │   ├── components/           # React components
│   │   │   ├── AddCredentials.js
│   │   │   ├── AddCustomer.js
│   │   │   ├── AddProduct.js
│   │   │   ├── AddPurchase.js
│   │   │   ├── AddSupplier.js
│   │   │   ├── AdminDashboard.js
│   │   │   ├── AdminLayout.jsx
│   │   │   ├── AdvancedChatbot.js
│   │   │   ├── Chatbot.js
│   │   │   ├── FloatingChatbot.js
│   │   │   └── ... (more components)
│   │   ├── App.js                # Main App component
│   │   ├── App.css
│   │   ├── index.js
│   │   └── index.css
│   └── package.json
│
├── .gitignore
└── README.md
```

## 🔐 Security Features

- **Password Hashing**: Bcrypt for secure password storage
- **JWT Authentication**: Secure token-based authentication
- **Email Verification**: Email-based password reset
- **Role-Based Access**: Different access levels for admin and users
- **Input Validation**: Server-side validation for all inputs
- **CORS Protection**: Configured for secure cross-origin requests

## 📊 Key Modules

### 1. Inventory Management
- Add, edit, and delete medicines
- Track stock levels and expiry dates
- Batch number management
- Low stock alerts

### 2. Sales Module
- Create sales invoices
- Apply discounts and loyalty points
- Generate QR codes for invoices
- Automatic stock deduction

### 3. Purchase Module
- Record supplier purchases
- Update inventory automatically
- Track purchase history

### 4. Customer Management
- Customer registration
- Loyalty points tracking
- Purchase history
- Contact management

### 5. AI Chatbot
- Medicine information lookup
- Pharmacy-related queries
- Natural language processing
- Context-aware responses

## 🔄 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - User login
- `POST /api/auth/forgot-password` - Request password reset
- `POST /api/auth/reset-password` - Reset password

### Products
- `GET /api/products` - Get all products
- `POST /api/products` - Add new product
- `PUT /api/products/:id` - Update product
- `DELETE /api/products/:id` - Delete product

### Sales
- `GET /api/sales` - Get all sales
- `POST /api/sales` - Create new sale
- `GET /api/sales/:id` - Get sale by ID

### Customers
- `GET /api/customers` - Get all customers
- `POST /api/customers` - Add new customer
- `PUT /api/customers/:id` - Update customer

### Chatbot
- `POST /api/chatbot/chat` - Send message to chatbot

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👨‍💻 Author

**Vishal**
- GitHub: [@vishal261104](https://github.com/vishal261104)

## 🙏 Acknowledgments

- OpenAI for the GPT API
- Ant Design for UI components
- MongoDB team for the excellent database
- All contributors and supporters

## 📞 Support

For support, email support@pharmacy.com or open an issue in the repository.

## 🗺️ Roadmap

- [ ] Mobile app development
- [ ] Multi-pharmacy support
- [ ] Advanced analytics dashboard
- [ ] Prescription management
- [ ] Integration with payment gateways
- [ ] Barcode scanning for products
- [ ] SMS notifications
- [ ] Multi-language support

## 📸 Screenshots

*Coming soon - Add screenshots of your application here*

---

**Made with ❤️ for pharmacy management**
