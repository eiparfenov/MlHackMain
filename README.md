# RealityFirst

## Ml
Для запуска склонируйте гит репозиторий

cd ai_inference

pip install -r requirements.txt

Создать файл .env вида


ngrok_api_key=YOUR_NGROCK_API_KEY

bert_path=./Models/bert_sentiment

cb_object_path=./Models/cb_model_1.0_logical_object_extended_6depth.cbm

cb_relevant_path=./Models/cb_model_0.932_relevant_logical_6depth.cbm


пенести модели в папку Models

https://drive.google.com/file/d/1OnxzW-v15sMLyIB8Rh8nlRt7_AGpQ6Rr/view?usp=drive_link

https://drive.google.com/file/d/1-65OvVb_o3eYTZ-SHBmzHVHmluD7wvou/view?usp=sharing

https://drive.google.com/file/d/1oiRqE-zARlyEPrsXfueDy9-HZx02GxBz/view?usp=sharing



запустить командой

python3 inference.py


Для запуска обучающих ноутбуков необходимо  перейти по ссылке

https://colab.research.google.com/drive/1QKpXcnfJ-eEchv5K0qTup7puVkgFO3ON?usp=sharing

Bert_training_classify_is_positive ноутбук

Забрать датасеты

https://drive.google.com/file/d/1TjIoc14NMpBtYFU3nHlZuKMOgs7PY4Mg/view?usp=drive_link

https://drive.google.com/file/d/1HLGk8n0NgM8wklucK3MoKZxgkEgugMi-/view?usp=drive_link

и загрузить их в папку /content




разрешить монтирование гугл диска или создать папку /content/drive/MyDrive/Models


запустить нотбук


https://colab.research.google.com/drive/16aRcz65CeROYQV0Z0onXCiSTUTKwayT6?usp=drive_link

Catboost.ipynb

забрать датасеты

https://drive.google.com/file/d/1--6ER86RuFib0OKg0InWcjW-sE8JdaLW/view?usp=sharing

https://drive.google.com/file/d/1--ruWtD6r8tO3bfoiyv4nIKuYsBFjn7S/view?usp=sharing

и загрузить их в папку /content

в ячейке 5
column_name="object" для датасета с суффиксом object

column_name="is_relevant" для датасета с суффиксом relevant


разрешить монтирование гугл диска или создать папку /content/drive/MyDrive/Models

запустить ноутбук

ДЛЯ НОУТБУКОВ КОНФИГУРАЦИЯ НА T4

НОУТ ДЛЯ АУГМЕНТАЦИИ ДАТАСЕТА
https://colab.research.google.com/drive/1wiFt4TWfQQDE79JQrBFJ-MQGSsWlTIP5?usp=sharing


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
- `ConnectionStrings__NluService` - api для подключения к модели машинного обучения (менять в docker-compose в env вынести не успел). Модель принтит при запуске ссылку на ngrok тунель, который нужно вставить сюда.
### Немного пояснений
Для создания ручек использовался minimal api, посмотреть описание ручек можно по пути `/swagger`.

Для хранения данных использовался postgersql.

Для организации очереди к на отправку собщений к модели (чтобы ее не перегружать и на падать по timeout) использовался rabbitmq.
