FROM python:3 AS builder
RUN apt-get update -y && apt-get install -y build-essential
WORKDIR /app 
COPY . /app

FROM python:slim
WORKDIR /app
COPY --from=builder /app /app
RUN pip install -r r.txt
EXPOSE 81
CMD ["python", "app.py"]