# Project Deployment Guide

This document provides setup and deployment instructions for **Frontend**, **Backend**, and **Admin Panel**.

---

## 📌 Frontend

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

---

## 📌 Backend

### Environment Variables

Create a `.env` file in the backend root directory with the following variables (example):

```env
PORT=4000
NODE_ENV=production
MONGODB_URL_PROD=
JWT_SECRET=YourSecretKeyHere
JWT_EXPIRY=7d
```

### Installation & Run Commands

```bash
# Install dependencies
npm install

# Run backend server
npm start
```

---

## 📌 Admin Panel

### Environment Variables

Create a `.env` file in the admin root directory with the following variables (example):

```env
VITE_API_BASE_URL=http://localhost:4000
```

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
