FROM python:3.12

RUN apt-get update && apt-get install -y ca-certificates && rm -rf /var/lib/apt/lists/*

WORKDIR /app

COPY requirements.txt .

RUN pip install --trusted-host pypi.org --trusted-host files.pythonhosted.org -r requirements.txt --no-cache-dir

RUN pip install --trusted-host pypi.org --trusted-host files.pythonhosted.org gunicorn==23.0.0

COPY . .

RUN chmod +x entrypoint.sh

CMD ["./entrypoint.sh"]