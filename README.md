# MERN Stack E-Commerce Project

A full-stack e-commerce application built using the MERN (MongoDB, Express.js, React.js, Node.js) stack. This project implements essential e-commerce functionalities including user authentication, product management, shopping cart features, and secure payment processing.

## Features

- **User Authentication**
  - Register/Login functionality
  - JWT-based authentication
  - Password encryption using bcrypt
  - Role-based authorization (Admin/User)

- **Product Management**
  - Browse products with pagination
  - Product categories and filtering
  - Product search functionality
  - Product details view
  - Admin product CRUD operations

- **Shopping Cart**
  - Add/Remove items
  - Adjust quantities
  - Persistent cart storage
  - Price calculations

- **Order Management**
  - Order creation and tracking
  - Order history
  - Admin order management
  - Order status updates

- **Payment Integration**
  - Secure payment processing
  - Multiple payment options
  - Payment status tracking

## Tech Stack

### Frontend
- React.js
- Redux for state management
- React Router for routing
- Axios for API calls
- Material-UI/Bootstrap for styling
- React-Toastify for notifications

### Backend
- Node.js
- Express.js
- MongoDB with Mongoose
- JWT for authentication
- Bcrypt for password hashing
- Multer for file uploads

## Prerequisites

Before running this project, make sure you have the following installed:
- Node.js (v14+ recommended)
- MongoDB
- npm or yarn
- Git

## Installation

1. Clone the repository
```bash
git clone https://github.com/Chandrateja1212/mern_stack_project.git
cd mern_stack_project
```

2. Install backend dependencies
```bash
cd backend
npm install
```

3. Install frontend dependencies
```bash
cd frontend
npm install
```

4. Create a .env file in the backend directory with the following variables
```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
```

5. Create a .env file in the frontend directory
```env
REACT_APP_API_URL=http://localhost:5000
```

## Running the Application

1. Start the backend server
```bash
cd backend
npm start
```

2. Start the frontend development server
```bash
cd frontend
npm start
```

3. Access the application at `http://localhost:3000`

## Project Structure

```
mern_stack_project/
├── backend/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── config/
│   └── server.js
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── redux/
│   │   ├── utils/
│   │   └── App.js
│   └── package.json
└── README.md
```

## API Endpoints

### Authentication Routes
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/profile` - Get user profile

### Product Routes
- `GET /api/products` - Get all products
- `GET /api/products/:id` - Get single product
- `POST /api/products` - Create new product (Admin)
- `PUT /api/products/:id` - Update product (Admin)
- `DELETE /api/products/:id` - Delete product (Admin)

### Order Routes
- `POST /api/orders` - Create new order
- `GET /api/orders` - Get user orders
- `GET /api/orders/:id` - Get single order
- `PUT /api/orders/:id` - Update order status (Admin)

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Database Schema

### User Schema
```javascript
{
  name: String,
  email: String,
  password: String,
  role: String,
  createdAt: Date
}
```

### Product Schema
```javascript
{
  name: String,
  description: String,
  price: Number,
  category: String,
  stock: Number,
  images: [String],
  createdAt: Date
}
```

### Order Schema
```javascript
{
  user: ObjectId,
  products: [{
    product: ObjectId,
    quantity: Number
  }],
  totalAmount: Number,
  status: String,
  createdAt: Date
}
```

## Future Enhancements

- [ ] Implement real-time order tracking
- [ ] Add product reviews and ratings
- [ ] Integrate multiple payment gateways
- [ ] Add wishlist functionality
- [ ] Implement social media authentication
- [ ] Add email notifications
- [ ] Implement chat support

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Thanks to all contributors who helped in building this project
- Special thanks to the MERN stack community for their excellent documentation and resources
