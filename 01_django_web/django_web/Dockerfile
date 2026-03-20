FROM python:3.12-slim

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

COPY . .

WORKDIR /app

COPY requirements.txt .

RUN pip install --upgrade pip 
RUN pip install -r requirements.txt

RUN mkdir -p /app/staticfiles

EXPOSE 8000

CMD ["gunicorn","--bind","0.0.0.0:8000","django_web.wsgi"]