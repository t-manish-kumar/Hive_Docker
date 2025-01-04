FROM python:3.12-slim

# Set the working directory
WORKDIR /app

# Copy necessary files
COPY requirements.txt /app/
COPY devops /app/

# Install necessary packages
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    python3 -m venv /opt/venv && \
    /opt/venv/bin/pip install --no-cache-dir -r requirements.txt

# Activate the virtual environment in the PATH
ENV PATH="/opt/venv/bin:$PATH"

# Expose the application port
EXPOSE 8000

# Default command to run the Django app
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
