FROM python:3.11-slim

WORKDIR /app

# Install psycopg2 dependencies
RUN apt-get update && apt-get install -y gcc libpq-dev

COPY ../requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY . .