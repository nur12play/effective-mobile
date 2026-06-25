# Effective Mobile — DevOps тестовое задание

## Технологии
- Python 3.11 (http.server)
- Nginx 1.25
- Docker & Docker Compose

## Структура проекта
├── backend/
│   ├── Dockerfile
│   └── app.py
├── nginx/
│   └── nginx.conf
├── docker-compose.yml
└── README.md

## Как запустить

docker compose up --build

## Как проверить

curl http://localhost:8000

## Примечание по порту

В задании указан порт 80. На Windows порт 80 занят системным
процессом (PID 4, NT Kernel & System), поэтому использовал
порт 8000. На Linux/Mac команда будет:

curl http://localhost


## Архитектура
- **nginx** принимает запросы снаружи
- **backend** недоступен с хоста, работает только внутри docker-сети
- nginx проксирует запросы на backend по имени сервиса

## Схема взаимодействия

[User] --HTTP--> [nginx:8000] --proxy_pass--> [backend:8080]