FROM python:3.11-slim

WORKDIR /app

COPY app.py .

EXPOSE 8080

RUN useradd -m appuser
USER appuser

CMD ["python", "app.py"]