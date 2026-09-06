FROM public.ecr.aws/docker/library/python:3.10-alpine

WORKDIR /app

RUN apk update && apk add --no-cache \
    build-base \
    gcc \
    linux-headers \
    libffi-dev

COPY requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt

COPY . /app

EXPOSE 5000

ENV FLASK_APP=app.py
ENV FLASK_RUN_HOST=0.0.0.0

CMD ["python3", "-m", "flask", "run", "--port=5000"]
