<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>


### about repositori
menggunakan laravel 11, projek sederhana RestApiEcomerce dengan auth JWT

# list api

  - users
    - register
    ``` powershell
    Method POST
    http://127.0.0.1:8000/api/auth/register
    ```
    dengan contoh pengisian
    ``` json 
    {
      "name": "test",
      "email": "testcustommer@gmail.com",
      "role": "custommer",
      "password": "passwordcoba",
      "password_confirmation": "passwordcoba"
    }
    ```
    - login
    ``` powershell
    Method POST
    http://127.0.0.1:8000/api/auth/login
    ```
    dengan contoh pengisian
    ``` json
    {
      "email": "customer11@gmail.com",
      "password": "passwordcoba"
    }
    ```
    - get info user yang sudang login
    ``` powershell
    Method GET
    http://127.0.0.1:8000/api/auth/me?

    dengan menambhkan token Authorization bearer "token"
    ```
  
  - Product(token Required)
    - GetAllProductsForSeller
    `` powershell
    Method GET
    http://localhost:8000/api/v1/seller/products
    ```
    - Create Product (Only Role Seller)
    ``` powershell
    Method POST
    http://localhost:8000/api/v1/products/
    ```
    dengan froarmat pengisian
    ``` json
    {
      "category_id" : 1,
      "name" : "kulkas",
      "description" : "peti ais",
      "price" : 300,
      "stock" : 120,
      "image" : "https://placehold.co/200x900"
    }
    ```
    -Mendapatkan Product berdasarkan id
    ``` powershell
    Method GET 
    http://127.0.0.1:8000/api/v1/product/4
    ```
    -update product 
    ``` powershell
    Method PUT
    http://127.0.0.1:8000/api/v1/products/4
    ```
    dengan contoh pengisian 
    ``` json
    {
      "description": "this is bag for high schooll"
    }
    ```
    - Mendapatkan semua product
    ``` powershell
    Method GET
    http://localhost:8000/api/v1/products/
    ```
    - Delete Product
    ``` powershell
    Method DELETE
    http://localhost:8000/api/v1/products/6
    ```
    - mengambil detail product berdasarkan ID
    Method GET
    http://localhost:8000/api/v1/detail/products/1
    ```
  
  - Cart(Keranjang)
    - Mengambil data keranjang
    ``` powershell
    Method GET
    http://localhost:8000/api/v1/carts/
    ```
    - Membuat product 
    ``` powerShell
    Method POST
    http://localhost:8000/api/v1/carts/

    include update carts
    ```
    dengan contoh pengisian
    ``` json
    {
      "product_id" : 5,
      "quantity" : 2     
    }
    ```
    - mengahpus Cart
    ``` powershell
     Method DELETE 
    http://localhost:8000/api/v1/carts/11
    ```
  - Orders
    - mendapatkan info Order
    ``` powerShell
    Method GET
    http://127.0.0.1:8000/api/v1/orders
    ```
    - membuat order berdasarkan id cart
    ``` powersell
    method POST
    http://127.0.0.1:8000/api/v1/orders
    ```
    - membuat semua oders yang ada di carts
    ``` powershell
    Method POST
    http://127.0.0.1:8000/api/v1/store/orders
    ```
    - update status (Only role Seller)
    ``` powershell
    Method put
    http://127.0.0.1:8000/api/v1/orders/{id}/status
    ```


