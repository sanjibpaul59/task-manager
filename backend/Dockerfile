FROM python:3.12-slim

# Set working directory
WORKDIR /usr/src/app

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Install libraries for mysqlclient
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    gcc \
    pkg-config \
    libmariadb-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*


# Install dependencies
COPY ./requirements.txt /usr/src/app/
RUN pip install --no-cache-dir -r requirements.txt

# Copy project
COPY . /usr/src/app/

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]