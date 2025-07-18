# Описание бота

## Основной функционал
1. **Управление пользователями**
   - Регистрация и управление профилями пользователей
   - Реферальная система с отслеживанием приглашенных пользователей
   - Управление балансом пользователей
   - Управление премиум-подписками

2. **Интеграция платежных систем**
   - Поддержка нескольких платежных провайдеров:
     - MulenPay (СБП)
     - Heleket (криптовалютные платежи)
   - Функционал пополнения баланса
   - Отслеживание истории транзакций

3. **Интеграция с Fragment API**
   - Система покупки звезд
   - Активация премиум-подписки
   - Аутентификация через JWT токен
   - 
## Премиум функции
1. **Тарифные планы**
   - 3 месяца (799)
   - 6 месяцев (1499)
   - 12 месяцев (2499)

2. **Система звезд**
   - Множество вариантов пакетов звезд:
     - Малые пакеты: 50, 75, 100, 150, 250
     - Средние пакеты: 350, 500, 750, 1000, 1500
     - Большие пакеты: 2500, 5000, 10000, 25000, 35000
     - Премиум пакеты: 50000, 100000, 150000, 500000, 1000000
   - Цена за звезду: 1.8

## Функции админ-панели
1. **Управление пользователями**
   - Просмотр профилей пользователей
   - Управление балансами пользователей
   - Отслеживание реферальных связей
   - Мониторинг премиум-подписок

2. **Управления Ценами**
   - Управления ценами на звезды/премиум тарифы

3. **Конфигурация системы**
   - Управление настройками платежных провайдеров
   - 
## Настройка окружения
Необходимые переменные окружения:
```
# Конфигурация бота
BOT_TOKEN=ваш_токен_бота
ADMIN_ID=ваш_id_админа

# База данных
POSTGRES_DSN=ваша_строка_подключения_postgres
REDIS_URL=ваш_url_redis

# Fragment API
FRAGMENT_API_KEY=ваш_api_ключ
FRAGMENT_SHOP_ID=ваш_id_магазина
FRAGMENT_PHONE_NUMBER=ваш_номер_телефона
FRAGMENT_MNEMONICS=ваши_мнемоники
FRAGMENT_JWT_TOKEN=ваш_jwt_токен

# Платежные системы
CRYPTOMUS_API_KEY=ваш_ключ
CRYPTOMUS_MERCHANT_ID=ваш_id_мерчанта
CRYPTOMUS_WEBHOOK_SECRET=ваш_секрет_вебхука

MULENPAY_API_KEY=ваш_ключ
MULENPAY_SECRET_KEY=ваш_секретный_ключ
MULENPAY_SHOP_ID=ваш_id_магазина
MULENPAY_MERCHANT_ID=ваш_id_мерчанта
MULENPAY_WEBHOOK_SECRET=ваш_секрет_вебхука
MULENPAY_CALLBACK_URL=ваш_url_обратного_вызова

HELEKET_API_KEY=ваш_ключ
HELEKET_MERCHANT_ID=ваш_id_мерчанта
HELEKET_CALLBACK_URL=ваш_url_обратного_вызова

# Другие настройки
NEWS_CHANNEL_ID=ваш_id_канала
NEWS_CHANNEL_LINK=ваша_ссылка_на_канал
WELCOME_IMAGE_URL=ваше_приветственное_изображение
WELCOME_DESCRIPTION=ваш_приветственный_текст
PROFILE_OFFER_URL=ваша_ссылка_на_оферту
PROFILE_PRIVACY_URL=ваша_ссылка_на_политику_конфиденциальности
SUPPORT_URL=ваша_ссылка_на_поддержку
```

## Инструкция по получению JWT токена Fragment API
1. Создайте файл `.env` с необходимыми переменными:
   ```
   FRAGMENT_API_KEY=ваш_api_ключ
   FRAGMENT_PHONE_NUMBER=ваш_номер_телефона
   FRAGMENT_MNEMONICS=ваши_мнемоники
   ```

2. Запустите скрипт `fragment_get_token.py`:
   ```bash
   python fragment_get_token.py
   ```

3. Скрипт автоматически:
   - Получит JWT токен
   - Добавит его в файл `.env` как `FRAGMENT_JWT_TOKEN`
   - Выведет токен в консоль

## Применение миграций
Для применения миграций и создания/обновления структуры базы данных используйте Alembic:

1. Убедитесь, что в .env корректно указан POSTGRES_DSN (строка подключения к вашей базе данных).
2. Откройте терминал в папке проекта.
3. Выполните команду:
   ```sh
   alembic upgrade head
   ```

Если alembic не установлен, установите его:
```sh
pip install alembic
```

Миграции будут применены, и база данных будет готова к работе.

## Запуск бота

1. Убедитесь, что все переменные окружения в .env заполнены корректно.
2. Установите зависимости:
   ```sh
   pip install -r requirements.txt
   ```
3. Запустите бота командой:
   ```sh
   python main.py
   ```

Бот будет запущен и готов к работе! 

## Ссылки на платежные системы
- MulenPay: https://mulenpay.ru/
- Heleket: https://heleket.com/

## Документация Fragment API
- Документация: https://fragment-api.com/

## Автор и поддержка
Автор: 🩸Chester #LTSDEV🩸
Поддержка автора:
- USDT TRC-20: TVuiCDMuvuxkMSkRVfYTB1fwTKkxxavdas

## Обратная связь и помощь
Если у вас есть предложения по улучшению бота или вы нашли ошибку — пишите в Telegram: https://t.me/YOCHESTER

Помощь с установкой бота на сервер или хостинг — 10$. 
