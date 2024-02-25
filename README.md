# api
//initializing a new Node.Js project
mkdir commerce-api
cd ecommerce-api
npm init -y
//now install the necessary dependencies
npm install express pg jsonwebtoken bcryptjs express-validator
//the next step is to set up the project structure
//creating the database schema
//Create a PostgreSQL database schema by executing the sql commamnds in 'db/schema.sql'
//implementing the backend
//Server configuration
//Server Configuration(server.js)
const express = require('express');
const app = express();
const PORT = process.env.PORT || 3000;

// Middleware
app.use(express.json());

// Routes
const authRoutes = require('./src/routes/authRoutes');
const productRoutes = require('./src/routes/productRoutes');
const orderRoutes = require('./src/routes/orderRoutes');

app.use('/api/auth', authRoutes);
app.use('/api/products', productRoutes);
app.use('/api/orders', orderRoutes);

app.listen(PORT, () => {
    console.log(`Server is running on port ${PORT}`);
});

