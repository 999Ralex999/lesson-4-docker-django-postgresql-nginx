# Docker: Django + PostgreSQL + Nginx

📦 **Проєкт з контейнеризації веб-застосунку на Django з використанням Docker Compose**

---

## 🛠 Стек технологій:

- Django 4.2
- PostgreSQL 14
- Nginx
- Docker / Docker Compose

---

## 🔧 Що реалізовано:

- Контейнерізовано Django-проєкт із підключенням до бази PostgreSQL
- Додано Nginx як проксі-сервер перед Django
- Налаштовано `docker-compose.yml` для автоматичного запуску усіх сервісів
- Конфігурація через `.env` (використовується в `settings.py`)
- Виведення веб-застосунку на хост через порт 80

---

## ⚠️ Особливості запуску:

1. **Обов’язково додати свій локальний IP-адрес до `ALLOWED_HOSTS`** у файлі `settings.py`:
   ```python
   ALLOWED_HOSTS = ["на свій IP-адрес"]
   
2. При першому запуску можлива помилка 502, якщо база PostgreSQL ще не готова.
🔁 Рішення:

Зупинити всі контейнери:
- docker compose down

Запустити базу й Django окремо:
- docker compose up db django

В іншому терміналі застосувати міграції:
- docker exec -it django_app python manage.py migrate

Потім запустити повністю:
- docker compose up -d

---

## 📂 Структура проєкту:

├── django/

│   ├── app/            # Django-проєкт

│   ├── manage.py

│   └── requirements.txt

├── nginx/

│   └── default.conf    # Nginx конфіг

├── .env

├── Dockerfile

└── docker-compose.yml

---

## 🧠 Що я вивчив:
Створення багатоконтейнерного середовища з Docker Compose

Підключення Django до PostgreSQL через .env

Роль та конфігурація Nginx як реверс-проксі

Обробка помилок запуску (502 Bad Gateway, DisallowedHost)

Публікація проєкту на GitHub у вигляді портфоліо

---

## 👨‍💻 Автор:

Олександр Ребенок

GitHub: github.com/999Ralex999

