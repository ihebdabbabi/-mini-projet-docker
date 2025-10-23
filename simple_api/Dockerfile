FROM python:3.8-slim-bullseye

LABEL maintainer="Iheb DABBABI"

WORKDIR /app

COPY requirements.txt student_age.py .

RUN apt update -y && apt install -y \
    python3-dev \
    libsasl2-dev \
    libldap2-dev \
    libssl-dev \
    gcc \
    && rm -rf /var/lib/apt/lists/*

RUN pip3 install --no-cache-dir -r requirements.txt

RUN mkdir -p /data
VOLUME ["/data"]

EXPOSE 5000

CMD ["python3", "student_age.py"]


#curl -u toto:python -X GET http://192.168.56.100:5000/pozos/api/v1.0/get_student_ages