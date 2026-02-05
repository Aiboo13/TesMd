<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

# 🛒 RestApiEcommerce

REST API sederhana untuk sistem e-commerce menggunakan:

- Laravel 11
- JWT Authentication
- Role: `seller` dan `customer`

---

# ⚙️ Instalasi & Menjalankan Project

```bash
git clone <repo-url>
cd nama-project
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
php artisan serve
```

---

# 🔐 Authentication (Users)

Base URL:
```
http://127.0.0.1:8000/api/auth
```

## 1. Register

**POST** `/register`

```json
{
  "name": "test",
  "email": "testcustomer@gmail.com",
  "role": "customer",
  "password": "passwordcoba",
  "password_confirmation": "passwordcoba"
}
```

---

## 2. Login

**POST** `/login`

```json
{
  "email": "customer11@gmail.com",
  "password": "passwordcoba"
}
```

Response akan mengembalikan JWT token.

---

## 3. Get User (Authenticated)

**GET** `/me`

Header:
```
Authorization: Bearer {token}
```

---

# 📦 Product (Token Required)

Base URL:
```
http://localhost:8000/api/v1
```

## 1. Get All Products (Public)

**GET** `/products`

---

## 2. Get Product by ID

**GET** `/product/{id}`

Contoh:
```
/product/4
```

---

## 3. Get Product Detail

**GET** `/detail/products/{id}`

---

## 4. Get Products for Seller

**GET** `/seller/products`

Token required.

---

## 5. Create Product (Role: Seller Only)

**POST** `/products`

```json
{
  "category_id": 1,
  "name": "kulkas",
  "description": "peti ais",
  "price": 300,
  "stock": 120,
  "image": "https://placehold.co/200x900"
}
```

---

## 6. Update Product

**PUT** `/products/{id}`

```json
{
  "description": "this is bag for high school"
}
```

---

## 7. Delete Product

**DELETE** `/products/{id}`

---

# 🛒 Cart (Keranjang)

Base URL:
```
/api/v1/carts
```

Token required.

## 1. Get Cart

**GET** `/carts`

---

## 2. Add / Update Cart

**POST** `/carts`

```json
{
  "product_id": 5,
  "quantity": 2
}
```

---

## 3. Delete Cart

**DELETE** `/carts/{id}`

---

# 📦 Orders

Base URL:
```
/api/v1
```

Token required.

## 1. Get Orders

**GET** `/orders`

---

## 2. Create Order (From Cart ID)

**POST** `/orders`

---

## 3. Create Order from All Carts

**POST** `/store/orders`

---

## 4. Update Order Status (Seller Only)

**PUT** `/orders/{id}/status`

---

# 🧠 Role System

- `seller` → Bisa CRUD product dan update status order
- `customer` → Bisa tambah cart dan membuat order

