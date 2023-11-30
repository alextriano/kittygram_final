FROM python:3.9
WORKDIR /app
COPY requirements.txt .
ENV PIP_ROOT_USER_ACTION=ignore
RUN pip install -r requirements.txt --no-cache-dir
COPY . .
CMD ["gunicorn", "--bind", "0.0.0.0:9000", "kittygram_backend.wsgi"]
