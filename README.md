# FAQ Management System

This is a Django-based FAQ Management System that supports multi-language translations, a REST API, and a user-friendly admin interface. It also includes a simple frontend for adding and viewing FAQs.

## Features
- **Multi-language Support**: FAQs can be translated into multiple languages (English, Hindi, Bengali, Telugu).
- **REST API**: Fetch FAQs in different languages using the API.
- **WYSIWYG Editor**: Use CKEditor for formatting FAQ answers.
- **Caching**: Redis is used for caching translations to improve performance.
- **Docker Support**: Easily deploy the application using Docker.
- **Admin Panel**: Manage FAQs through the Django admin interface.

## Table of Contents
- [Installation](#installation)
- [Running the Application](#running-the-application)
- [API Usage](#api-usage)
- [Docker Deployment](#docker-deployment)
- [Contributing](#contributing)
- [License](#license)
- [Submission Checklist](#submission-checklist)

## Submission Checklist

### 1. **Model Design**
- [✔] Create a model to store FAQs.
- [✔] Each FAQ should have:
  - A question (TextField)
  - An answer (RichTextField for WYSIWYG editor support)
  - Language-specific translations (question_hi, question_bn, etc.)
- [✔] Implement a model method to retrieve translated text dynamically.

### 2. **WYSIWYG Editor Integration**
- [✔] Use `django-ckeditor` to allow users to format answers properly.
- [✔] Ensure that the WYSIWYG editor supports multilingual content.

### 3. **API Development**
- [✔] Create a **REST API** for managing FAQs.
- [✔] Support language selection via `?lang=` query parameter.
- [✔] Ensure responses are fast and efficient using pre-translation.

### 4. **Caching Mechanism**
- [✔] Implement **cache framework** to store translations.
- [✔] Use Redis for improved performance.

### 5. **Multi-language Translation Support**
- [✔] Use Google Translate API or `googletrans` for translations.
- [✔] Automate translations during object creation.
- [✔] Provide fallback to English if translation is unavailable.

### 6. **Admin Panel**
- [✔] Register the FAQ model in the Admin site or create one separately.
- [✔] Enable a user-friendly admin interface for managing FAQs.

### 7. **Unit Tests & Code Quality**
- [✔] Write unit tests using pytest (or mocha/chai).
- [✔] Ensure tests cover model methods and API responses.
- [✔] Follow PEP8/ES6 guidelines and use flake8/JS tools for linting.

### 8. **Documentation**
- [✔] Write a detailed README with:
  - Installation steps
  - API usage examples
  - Contribution guidelines
- [✔] Ensure the README is well-structured and easy to follow.

### 9. **Git & Version Control**
- [✔] Use Git for version control.
- [✔] Follow conventional commit messages:
  - `feat`: Add multilingual FAQ model
  - `fix`: Improve translation caching
  - `docs`: Update README with API examples
- [✔] Ensure atomic commits with clear commit messages.

### 10. **Deployment & Docker Support (Bonus)**
- [✔] Provide a Dockerfile and `docker-compose.yml`.
- [✔] Deploy the application to Heroku or AWS (optional).

## Installation

### Prerequisites
- Python 3.9 or higher
- Docker (optional, for containerized deployment)
- Redis (for caching)

### Steps
1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/faq_project.git
    cd faq_project
    ```

2. Create a virtual environment:
    ```bash
    python -m venv env
    source env/bin/activate  # On Windows: env\Scripts\activate
    ```

3. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

4. Set up environment variables:
    Create a `.env` file in the root directory:
    ```env
    SECRET_KEY=your-secret-key
    DEBUG=True
    ALLOWED_HOSTS=localhost,127.0.0.1
    DATABASE_URL=sqlite:///db.sqlite3
    REDIS_URL=redis://127.0.0.1:6379/0
    ```

5. Apply migrations:
    ```bash
    python manage.py migrate
    ```

6. Create a superuser:
    ```bash
    python manage.py createsuperuser
    ```

7. Collect static files:
    ```bash
    python manage.py collectstatic
    ```

## Running the Application

### Development Server
1. Start the development server:
    ```bash
    python manage.py runserver
    ```

2. Access the application at:
    ```
    http://localhost:8000/
    ```

3. Access the admin panel at:
    ```
    http://localhost:8000/admin/
    ```

### Docker
1. Build and start the containers:
    ```bash
    docker-compose up --build
    ```

2. Access the application at:
    ```
    http://localhost:8000/
    ```

3. To stop the containers:
    ```bash
    docker-compose down
    ```

## API Usage

### Endpoints
- Fetch FAQs in English (default):
    ```bash
    curl http://localhost:8000/api/faqs/
    ```

- Fetch FAQs in Hindi:
    ```bash
    curl http://localhost:8000/api/faqs/?lang=hi
    ```

- Fetch FAQs in Bengali:
    ```bash
    curl http://localhost:8000/api/faqs/?lang=bn
    ```

- Fetch FAQs in Telugu:
    ```bash
    curl http://localhost:8000/api/faqs/?lang=te
    ```

### Example Response
```json
[
    {
        "id": 1,
        "question": "What is Django?",
        "answer": "Django is a web framework.",
        "question_hi": "Django क्या है?",
        "question_bn": "জ্যাঙ্গো কী?",
        "question_te": "డ్యాంగో అంటే ఏమిటి?",
        "answer_hi": "Django एक वेब फ्रेमवर्क है।",
        "answer_bn": "জ্যাঙ্গো একটি ওয়েব ফ্রেমওয়ার্ক।",
        "answer_te": "డ్యాంగో ఒక వెబ్ ఫ్రేమ్‌వర్క్."
    }
]
