FROM python:latest

WORKDIR /app

COPY requirements.txt /app/
RUN pip install -r requirements.txt

COPY . /app/

EXPOSE 8000

COPY entrypoint.sh /entrypoint.sh

RUN apt-get update && apt-get install -y netcat-openbsd && rm -rf /var/lib/apt/lists/*

RUN chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
