FROM python:3.9-slim

# Set working directory
WORKDIR /app

# Install system dependencies (optional, good for psycopg2/Postgres)
RUN apt-get update && apt-get install -y \
    gcc libpq-dev && \
    rm -rf /var/lib/apt/lists/*

# Copy requirements first (better caching)
COPY requirements.txt .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY . .

# Expose port (if your app runs on 8000 for example)
EXPOSE 8000

# Default command to run app
CMD ["python", "main.py"]
