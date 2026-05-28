# Online Kirana Store

A full-stack grocery e-commerce application built with the MERN stack. Customers can browse products by category, manage a cart, and checkout via cash on delivery or Stripe. Sellers get a dedicated dashboard to manage products and view orders.

## Features

**Customers**
- Register / login with JWT-based authentication
- Browse products and filter by category
- Add to cart, manage quantities, and place orders
- Save multiple delivery addresses
- Pay via Cash on Delivery or Stripe
- View order history and status

**Sellers**
- Secure seller dashboard
- Add products with up to 4 images (stored on Cloudinary)
- Manage inventory and stock
- View and manage incoming orders

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React 19, Vite, Tailwind CSS v4, React Router v7 |
| Backend | Node.js, Express 5 |
| Database | MongoDB, Mongoose |
| Auth | JWT, bcryptjs, cookie-parser |
| Payments | Stripe |
| Image Storage | Cloudinary, Multer |
| HTTP Client | Axios |

## Project Structure

```
online-kirana-store/
├── backend/
│   ├── config/         # DB, Cloudinary, Multer setup
│   ├── controller/     # Business logic (user, product, order, cart, address)
│   ├── middlewares/    # Auth guards (authUser, authSeller)
│   ├── models/         # Mongoose schemas
│   ├── routes/         # API routes
│   └── index.js        # Express entry point
└── client/
    ├── src/
    │   ├── components/ # Navbar, Banner, ProductCard, Footer, etc.
    │   ├── pages/      # Home, Products, Cart, MyOrders, etc.
    │   ├── context/    # Global app state
    │   └── App.jsx     # Route definitions
    └── index.html
```

## Getting Started

### Prerequisites

- Node.js 18+
- MongoDB (local or Atlas)
- Cloudinary account
- Stripe account (for online payments)

### 1. Clone the repository

```bash
git clone https://github.com/Divesh-G/GroceryApp.git
cd GroceryApp
```

### 2. Configure backend environment

Create `backend/.env` based on the template below:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
NODE_ENV=development

# Admin / Seller credentials
SELLER_EMAIL=admin@example.com
SELLER_PASSWORD=your_password

# Cloudinary
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

# Stripe
STRIPE_PUBLISHABLE_KEY=pk_test_...
STRIPE_SECRET_KEY=sk_test_...
```

### 3. Configure frontend environment

Create `client/.env`:

```env
VITE_BACKEND_URL=http://localhost:5000
```

### 4. Install dependencies and run

**Backend**

```bash
cd backend
npm install
npm run dev
```

**Frontend** (in a separate terminal)

```bash
cd client
npm install
npm run dev
```

The app will be available at `http://localhost:5173` with the API running on `http://localhost:5000`.

## Scripts

| Directory | Command | Description |
|---|---|---|
| `backend` | `npm run dev` | Start server with hot reload (nodemon) |
| `client` | `npm run dev` | Start Vite dev server |
| `client` | `npm run build` | Production build |
| `client` | `npm run preview` | Preview production build |
| `client` | `npm run lint` | Run ESLint |

## License

MIT
