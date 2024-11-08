FROM python:3.12-slim

# Install dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    default-libmysqlclient-dev \
    libpq-dev \
    curl \
    git \
    && apt-get clean

# Install Airflow and compatible pendulum version
RUN pip install apache-airflow[postgres,redis,celery]==2.7.0 \
    gunicorn flask-limiter \
    pendulum==2.1.2  # Explicit version to avoid conflict

# Expose ports
EXPOSE 8080
