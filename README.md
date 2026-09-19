# 📝 Restaurant Management System

A RESTful Restaurant Management System built using **Django REST Framework** that allows restaurants to manage menus, orders, tables, customers, staff, and payments through secure and role-based APIs.

## ✨ Features

* **Authentication:** Registration, Login, and Logout (Token Authentication and Password Hashing)
* **Role-Based Access Control:** Admin, Waiter, Chef, and Cashier roles utilizing Django Permissions
* **CRUD Operations:** Full management for Menu Items, Categories, Tables, Orders, and Customers via DRF APIs
* **Order Management:** Waiters can create and manage customer orders while chefs can update order preparation status
* **Order Status Tracking:** Track orders through Pending, Cooking, Ready, Served, Paid, and Cancelled states
* **Table Management:** Manage restaurant tables and their availability
* **Search & Filter:** Search menu items by name and category; filter orders by status and date
* **Pagination:** Clean, paginated responses for menu items, orders, and other listings
* **API Documentation:** Interactive Swagger UI and ReDoc endpoints
* **Email Notifications:** Automatic email notifications for relevant restaurant activities using Django Signals
* **Clean Architecture:** Well-commented and structured source code

## 🛠 Tech Stack

* Python
* Django
* Django REST Framework
* PostgreSQL
* Git & GitHub
* Postman

## 👥 User Roles

| Role        | Permissions                                                                 |
| ----------- | --------------------------------------------------------------------------- |
| **Admin**   | Full system access; manage users, menu, tables, orders, and restaurant data |
| **Waiter**  | Manage customer orders, view menu items, and update orders as served        |
| **Chef**    | View orders and update food preparation status                              |
| **Cashier** | View served orders, generate bills, and manage payments                     |

## 📂 Project Structure

```text
restaurant_management/
├── restaurant_app/
├── my_project/
├── users/
├── .gitignore
├── manage.py
└── requirements.txt
```

## 🗄 Database Design

The project consists of the following main entities:

* User (custom user with role)
* Profile
* Category
* MenuItem
* Table
* Order
* OrderItem
* Payment

### Relationships

* One User can manage multiple restaurant operations based on their assigned role.
* One Category can contain multiple Menu Items.
* One Table can have multiple Orders over time.
* One Customer Order can contain multiple Order Items.
* One Menu Item can be included in multiple Order Items.
* One Order is associated with one Table.
* One Order can have one Payment.
* One User can create and manage multiple Orders based on their role.

## 📋 Prerequisites

Make sure the following are installed on your system:

* Python 3.10+
* PostgreSQL
* Git
* pip (Python Package Manager)

## ⚙️ Installation

### Clone the Repository

```bash
git clone https://github.com/jilani-code369/restaurant-management.git
```

### Navigate to the Project Directory

```bash
cd restaurant-management
```

### Create a Virtual Environment

```bash
python -m venv venv
```

### Activate the Virtual Environment

```bash
venv\Scripts\activate (Windows)
```

```bash
source venv/Scripts/activate (Git Bash)
```

```bash
source venv/bin/activate  (Linux/macOS)
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Apply Database Migrations

```bash
python manage.py migrate
```

### Create a Superuser (Optional)

```bash
python manage.py createsuperuser
```

### Run the Development Server

```bash
python manage.py runserver
```

## 📄 API Endpoints

**Root URL**

[`http://127.0.0.1:8000/`](http://127.0.0.1:8000/)

### API Endpoints

| Method | Endpoint                                                          | Description                 |
| ------ | ----------------------------------------------------------------- | --------------------------- |
| POST   | [`/auth/register/`](http://127.0.0.1:8000/auth/register/)         | Register a new user         |
| POST   | [`/auth/login/`](http://127.0.0.1:8000/auth/login/)               | User login                  |
| POST   | [`/auth/logout/`](http://127.0.0.1:8000/auth/logout/)             | User logout                 |
| CRUD   | [`/api/v1/user/`](http://127.0.0.1:8000/api/v1/user/)             | User management             |
| CRUD   | [`/api/v1/menu-item/`](http://127.0.0.1:8000/api/v1/menu-item/)   | Menu item management        |
| CRUD   | [`/api/v1/category/`](http://127.0.0.1:8000/api/v1/category/)     | Menu category management    |
| CRUD   | [`/api/v1/table/`](http://127.0.0.1:8000/api/v1/table/)           | Restaurant table management |
| CRUD   | [`/api/v1/order/`](http://127.0.0.1:8000/api/v1/order/)           | Order management            |
| CRUD   | [`/api/v1/order-item/`](http://127.0.0.1:8000/api/v1/order-item/) | Order item management       |
| CRUD   | [`/api/v1/payment/`](http://127.0.0.1:8000/api/v1/payment/)       | Payment management          |

### Documentation API

| Endpoint                                                                  | Description              |
| ------------------------------------------------------------------------- | ------------------------ |
| [`/api/schema/`](http://127.0.0.1:8000/api/schema/)                       | OpenAPI Schema           |
| [`/api/schema/swagger-ui/`](http://127.0.0.1:8000/api/schema/swagger-ui/) | Swagger UI Documentation |
| [`/api/schema/redoc/`](http://127.0.0.1:8000/api/schema/redoc/)           | ReDoc Documentation      |

## 🔐 Environment Variables

Create a `.env` file and configure the following variables:

```text
SECRET_KEY=your_django_secret_key
DEBUG=True

DB_ENGINE=django.db.backends.postgresql
DB_NAME=your_db_name
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_HOST=localhost
DB_PORT=5432

CORS_ALLOW_ALL_ORIGINS=True

EMAIL_BACKEND=django.core.mail.backends.smtp.EmailBackend
EMAIL_PORT=587
EMAIL_USE_TLS=True
EMAIL_HOST=smtp.gmail.com
EMAIL_HOST_USER=your_email@gmail.com
EMAIL_HOST_PASSWORD=your_app_password
```

## 🧪 Testing

The APIs were tested using **Postman** to verify:

* Authentication
* Authorization
* CRUD Operations
* Order Management
* Menu Management
* Table Management
* Searching
* Filtering
* Pagination
* Payment Processing
* Error Handling

## 💡 Future Improvements

* JWT Authentication
* Online Food Ordering
* Image Upload for Menu Items
* Inventory and Stock Management
* Restaurant Sales Analytics
* Reservation and Table Booking System
* Use Django Groups for Role Based Access

## 👨‍💻 Author

**Jilani Nadaf**

Backend Developer

* [GitHub](https://github.com/jilani-code369/)
* [Email](mailto:nadafjilani182@gmail.com)
* [LinkedIn](https://www.linkedin.com/in/jilani-nadaf)

## 📄 License

This project is developed for educational purposes and internship submission.
