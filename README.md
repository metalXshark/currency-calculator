# Currency Calculator
Простой калькулятор валют, который позволяет пользователю конвертировать сумму из одной валюты в другую, используя актуальные курсы валют через API.

## Описание
Этот проект реализован с использованием Vue.js 3, Axios для запросов к API и Vue Router для управления страницами. Калькулятор валют использует API ExchangeRate-API для получения актуальных данных о курсах валют.

## Функции
Ввод суммы для конвертации.

Выбор исходной и целевой валюты.

Автоматическое получение актуальных курсов валют через API.

Отображение результата конверсии.

Обработка ошибок (например, если API не доступен).

## Стек технологий
Vue.js 3 — основной фреймворк для разработки интерфейса.

Axios — для отправки запросов к API.

Vue Router — для настройки роутинга (при необходимости, для расширения проекта).

ExchangeRate-API — API для получения курсов валют.

## Установка
Клонируйте репозиторий:

bash
git clone https://github.com/your-username/currency-calculator.git

Перейдите в директорию проекта:

bash
cd currency-calculator

Установите зависимости:

bash
npm install

## Получите свой API ключ с ExchangeRate-API и замените его в коде компонента CurrencyCalculator.vue (вставьте ваш ключ в URL API-запроса):

javascrip
const apiKey = 'your-api-key-here'; // Замените на свой API ключ
const response = await axios.get(
  `https://v6.exchangerate-api.com/v6/${apiKey}/latest/${this.fromCurrency}`
)
Запуск проекта
После установки всех зависимостей и настройки API-ключа, запустите проект локально:

bash
npm run serve
Перейдите в браузер по адресу http://localhost:8080, чтобы увидеть приложение.

## Как работает приложение?
При запуске на странице отображается калькулятор.

Пользователь вводит сумму, выбирает валюту для конвертации и целевую валюту.

Нажав на кнопку "Конвертировать", приложение отправляет запрос к API и получает актуальные курсы валют.

Приложение отображает результат конверсии на экране.

## Примечания
Чтобы проект работал, необходимо зарегистрироваться на ExchangeRate-API и получить API ключ.

В проекте использован Axios для асинхронных запросов, а также Vue Router для организации роутинга (хотя на данный момент используется только одна страница).

## Скриншоты
![Фото 1](https://github.com/metalXshark/currency-calculator/blob/master/photo/1.jpg)
![Фото 2](https://github.com/metalXshark/currency-calculator/blob/master/photo/2.jpg)
![Фото 3](https://github.com/metalXshark/currency-calculator/blob/master/photo/3.jpg)
![Фото 4](https://github.com/metalXshark/currency-calculator/blob/master/photo/4.jpg)

Автор: metalXshark
