FROM python:3.9-slim

WORKDIR /app

# 🔥 Installer dépendances système nécessaires à python-ldap
RUN apt-get update && apt-get install -y \
    gcc \
    build-essential \
    libldap2-dev \
    libsasl2-dev \
    libssl-dev \
    && rm -rf /var/lib/apt/lists/*

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 5000

CMD ["python", "student_age.py"]