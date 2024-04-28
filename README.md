# RealityFirst

## Frontend
Конфигурационный файл - next.config.mjs

MESSAGE_API - для отправки формы обратной связи\
OPTIONS_API - для получения данных по преподавателю, вебинару, курсу по обратной связи (для категоризации анализа)\
MODEL_API - получение данных для анализа

npm run dev - запуск в режиме разработчика\
npm run build - создание prod сборки\
npm run start - запуск prod сборки

## Backend
### Стек технологий
- asp net minimal api;
- postgresql
- rabbitmq
### Запуск
В папке `Backend` запустить `docker compose up`. Доступ к базе будет на порту 5431, сам сервис развернется на 5244.
### Конфигурация
- `ConnectionStrings__NluService` - api для подключения к модели машинного обучения (менять в docker-compose в env вынести не успел)
### Немного пояснений
Для создания ручек использовался minimal api, посмотреть описание ручек можно по пути `/swagger`.

Для хранения данных использовался postgersql.

Для организации очереди к на отправку собщений к модели (чтобы ее не перегружать и на падать по timeout) использовался rabbitmq.
