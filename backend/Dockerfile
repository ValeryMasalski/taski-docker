FROM python:3.11-slim
WORKDIR /app
RUN apt-get update && apt-get install -y \
    build-essential \
    libpq-dev \
 && rm -rf /var/lib/apt/lists/*
RUN pip install gunicorn==23.0.0
COPY requirements.txt .
RUN pip install -r requirements.txt --no-cache-dir
COPY . .
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]
