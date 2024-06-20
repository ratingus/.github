### Как развернуть проект?
1. Склонируйте этот репозиторий
2. Пройдите по `README.md` в подмодулях, чтобы запустить их:
    - [backend](https://github.com/ratingus/ratingus-backend/blob/main/README.md)
    - [web](https://github.com/ratingus/ratingus-web/blob/main/README.md)
    - [mobile](https://github.com/ratingus/ratingus_mobile/blob/main/README.md)
3. Можете настроить nginx, конфигурация которого находится в корне проекта. Также для этого придётся создать в docker сеть `ratingus-network`.

### Как это работает у нас?
1. Мы используем `docker-compose` nginx, backend, web для разворачивания проекта на сервере https://ratingus.fun
2. Backend и web имеют github actions с настроенным ci/cd с использованием Ansible. При push в dev ветку, происходит билд контейнеров и их деплой в ghcr, после этого запускается ansible-playbook для обновления контейнеров на сервере.