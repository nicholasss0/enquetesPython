# Escolha uma imagem Python
FROM python:3.13-rc-bookworm

WORKDIR /app


COPY requirements.txt /app/



RUN pip install --upgrade pip && \
    pip install -r requirements.txt

COPY . /app/

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
ENV PYTHONPATH=/app

EXPOSE 8000

CMD ["py", "manage.py", "runserver", "0.0.0.0:8000"]