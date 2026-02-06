FROM python:3.12

# Устанавливаем setuptools (включает distutils) перед установкой зависимостей
RUN pip install --upgrade pip setuptools wheel

WORKDIR /app
COPY requirements.txt .
RUN pip install gunicorn==23.0.0 
# Установка зависимостей
RUN pip install -r requirements.txt --no-cache-dir

COPY . .

# Команда для миграций и запуска сервера
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]