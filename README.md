# 📝 Learning Management System

A RESTful Learning Management System built using **Django REST Framework** that allows students to enroll in courses, instructors to manage educational content, sponsors to support students financially, and administrators to manage the overall learning platform.

## ✨ Features

* **Authentication:** Registration, Login, and Logout (Token Authentication and Password Hashing)
* **Role-Based Access Control:** Admin, Instructor, Student, and Sponsor roles utilizing Django Permissions
* **CRUD Operations:** Full management for Users, Courses, Lessons, Assignments, Enrollments, Sponsorships, and Notifications via DRF APIs
* **Course Management:** Instructors can create and manage their own courses, lessons, and assignments
* **Enrollment Management:** Students can enroll in available courses and track their learning progress
* **Assignment Management:** Students can submit assignments while instructors can review and evaluate submissions
* **Sponsorship System:** Sponsors can financially support students and track their sponsorships
* **Progress Tracking:** Track student course progress from 0% to 100%
* **Search & Filter:** Search courses by title and instructor; filter by difficulty, price, and course status
* **Pagination:** Clean, paginated responses for courses, users, and other listings
* **API Documentation:** Interactive Swagger UI and ReDoc endpoints
* **Email Notifications:** Automatic email notifications for relevant system activities using Django Signals
* **Clean Architecture:** Well-commented and structured source code

## 🛠 Tech Stack

* Python
* Django
* Django REST Framework
* PostgreSQL
* Git & GitHub
* Postman

## 👥 User Roles

| Role           | Permissions                                                                                  |
| -------------- | -------------------------------------------------------------------------------------------- |
| **Admin**      | Full system access; manage users, roles, courses, enrollments, and platform content          |
| **Instructor** | Create, update, and delete own courses, lessons, and assignments; review student submissions |
| **Student**    | View courses, enroll in courses, access lessons, submit assignments, and track progress      |
| **Sponsor**    | View available courses and students, provide sponsorship, and track sponsorship activities   |

## 📂 Project Structure

```text
lms/
├── course_img/
├── learning/
├── lms/
├── profie_pic/
├── submission_files/
├── users/
```

## 🗄 Database Design

The project consists of the following main entities:

* User (custom user with role)
* Course
* Enrollment
* Assignment
* Submission
* Evaluation
* Sponsorship
* Notification

### Relationships

* One Instructor can create multiple Courses.
* One Course can contain multiple Lessons.
* One Course can contain multiple Assignments.
* One Student can enroll in multiple Courses.
* One Course can have multiple Students through Enrollments.
* One Assignment can have multiple Submissions.
* One Student can submit assignments for enrolled courses.
* One Sponsor can have multiple Sponsorships.
* One Student can receive sponsorship from multiple Sponsors.
* One User can receive multiple Notifications.

## 📋 Prerequisites

Make sure the following are installed on your system:

* Python 3.10+
* PostgreSQL
* Git
* pip (Python Package Manager)

## ⚙️ Installation

### Clone the Repository

```bash
git clone https://github.com/jilani-code182/lms.git
```

### Navigate to the Project Directory

```bash
cd lms
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

| Method | Endpoint                                                              | Description                      |
| ------ | --------------------------------------------------------------------- | -------------------------------- |
| POST   | [`/auth/register/`](http://127.0.0.1:8000/auth/register/)             | Register a new user              |
| POST   | [`/auth/login/`](http://127.0.0.1:8000/auth/login/)                   | User login                       |
| POST   | [`/auth/logout/`](http://127.0.0.1:8000/auth/logout/)                 | User logout                      |
| CRUD   | [`/api/v1/user/`](http://127.0.0.1:8000/api/v1/profile/)                 | User management                  |
| CRUD   | [`/api/v1/course/`](http://127.0.0.1:8000/api/v1/course/)             | Course management                |
| CRUD   | [`/api/v1/assignment/`](http://127.0.0.1:8000/api/v1/assignment/)     | Assignment management            |
| CRUD   | [`/api/v1/submission/`](http://127.0.0.1:8000/api/v1/submission/)     | Assignment submission management |
| CRUD   | [`/api/v1/enrollment/`](http://127.0.0.1:8000/api/v1/enrollment/)     | Course enrollment management     |
| CRUD   | [`/api/v1/sponsorship/`](http://127.0.0.1:8000/api/v1/sponsorship/)   | Sponsorship management           |
| CRUD   | [`/api/v1/notification/`](http://127.0.0.1:8000/api/v1/notification/) | Notification management          |

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

>Note: Environment variables contain sensitive configuration values and are not included in the repository. The values shown above are placeholders and should be replaced with the appropriate local configuration.


## 🧪 Testing

The APIs were tested using **Postman** to verify:

* Authentication
* Authorization
* CRUD Operations
* Course Management
* Enrollment Management
* Assignment Submission
* Sponsorship Management
* Searching
* Filtering
* Pagination
* Notifications
* Error Handling

## 💡 Future Improvements

* JWT Authentication
* Course Certificates
* Video-Based Course Content
* Course Rating and Review System
* Learning Analytics and Progress Reports

## 👨‍💻 Author

**Jilani Nadaf**

Backend Developer

* [GitHub](https://github.com/jilani-code182/)
* [Email](mailto:nadafjilani182@gmail.com)
* [LinkedIn](https://www.linkedin.com/in/jilani-nadaf)

## 📄 License

This project is developed for educational purposes and internship submission.
