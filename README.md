# Project Deployment Guide

This document provides setup and deployment instructions for **Frontend**, **Backend**, and **Admin Panel**.

---

## 📌 Frontend

### Installation & Run Commands

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build
```

📂 After build, the output folder is `dist/`.

### Environment Variables

Create a `.env` file in the frontend root directory with the following variables (example):

```env
VITE_API_BASE_URL=http://localhost:4000
```

### ⚙️ Vite Config (allowedHosts setup)

Add the following in your `vite.config.js` file:

```js
export default defineConfig({
  server: {
    // 👇 Add your allowed host URLs here
    allowedHosts: ["localhost", "127.0.0.1", "example.com"],
  },
});
```

---

## 📌 Backend

### Installation & Run Commands

```bash
# Install dependencies
npm install

# Run backend server
npm start
```

### Environment Variables

Create a `.env` file in the backend root directory with the following variables (example):

```env
PORT=4000
NODE_ENV=production
MONGODB_URL_PROD=
JWT_SECRET=YourSecretKeyHere
JWT_EXPIRY=7d
```

### ⚙️ CORS Setup (Allowed Origins)

To enable CORS, add the following setup in your index.js or server.js:

```js
// ✅ Allowed origins (local + deployed)
const allowedOrigins = [
  "http://localhost:5173", // Vite React local
  "https://yourfrontend.com", // Deployed React app
];

// ✅ CORS setup
app.use(
  cors({
    origin: function (origin, callback) {
      if (!origin || allowedOrigins.includes(origin)) {
        callback(null, true);
      } else {
        callback(new Error("❌ Not allowed by CORS"));
      }
    },
    credentials: true, // if you're using cookies/auth headers
  })
);
```

---

## 📌 Admin Panel

### Installation & Run Commands

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build
```

📂 After build, the output folder is `dist/`.

### Environment Variables

Create a `.env` file in the admin root directory with the following variables (example):

```env
VITE_API_BASE_URL=http://localhost:4000
```

---
