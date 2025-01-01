# Telegram Weather Bot

## Опис
Telegram-бот для отримання поточної погоди через API OpenWeather.

## Як запустити проект

### Локальний запуск
1. Клонувати репозиторій:
   ```bash
   git clone https://github.com/RangerDnipro/Telegram_weather.git
   ```
2. Перейти в папку проекту:
   ```bash
   cd Telegram_weather
   ```
3. Створити віртуальне середовище:
   ```bash
   python -m venv env
   env\Scripts\activate
   ```
4. Встановити залежності:
   ```bash
   pip install -r requirements.txt
   ```
5. Створити файл `.env` у кореневій папці з наступним вмістом:
   ```plaintext
   API_KEY=<ключ_OpenWeather>
   TELEGRAM_BOT_TOKEN=<токен_бота>
   ```
6. Запустити бота:
   ```bash
   python bot.py
   ```

### Розгортання на Railway
1. Створити новий проект на Railway.
2. Підключити репозиторій через GitHub.
3. У налаштуваннях Railway додати змінні оточення:
   - `API_KEY`: ключ OpenWeather.
   - `TELEGRAM_BOT_TOKEN`: Telegram-бота.
4. Railway автоматично розгорне проект, використовуючи `Procfile`.

## Використані API
- **OpenWeather API**: для отримання інформації про погоду.
- **Telegram Bot API**: для створення Telegram-бота.

## Команди бота
- `/start` — Початок роботи з ботом.
- `/help` — Список доступних команд.
- `/weather` — Запит погоди. Бот запитує місто через кнопки або текстом і повертає поточну погоду.

## Приклади роботи
1. **Запит `/start`:**
   ```
   Користувач: /start
   Бот: Привіт! Я бот для отримання погоди. Напиши /help, щоб дізнатися більше.
   ```

2. **Запит `/weather` з кнопками:**
   ```
   Користувач: /weather
   Бот: Оберіть місто для отримання погоди або введіть інше місто з клавіатури:
   (Кнопки: Київ, Львів, Одеса, Харків, Дніпро)
   Користувач: [натискає Київ]
   Бот: Погода в Київ: +5°C, хмарно.
   ```

3. **Запит `/weather` з введенням міста вручну:**
   ```
   Користувач: /weather
   Бот: Оберіть місто для отримання погоди або введіть інше місто з клавіатури:
   Користувач: Берлін
   Бот: Погода в Берлін: +2°C, ясно.
   ```

4. **Невідома команда:**
   ```
   Користувач: /unknown_command
   Бот: Я не розумію цієї команди. Напишіть /help для перегляду доступних команд.
   ```

## Логування
- Логи зберігаються у файлі `app.log`.
- Записуються:
  - Успішні та неуспішні запити до API.
  - Вибір міст через кнопки та введення вручну.
  - Невідомі команди.
  - Використання кешованих результатів.

## Залежності
- Python 3.9+
- `python-telegram-bot`
- `requests`
- `python-dotenv`
