# LR3-diagram

## Диаграмма состояний ##

Диаграмма состояний UML представляет различные состояния и переходы в Telegram-боте для консультаций клиентов косметологической клиники. Она включает состояния, такие как просмотр новостей, просмотр услуг и выбор специалиста. Переходы показывают, как пользователь может перемещаться между этими состояниями на основе своих действий в Telegram-боте.

Диаграмма состоний Telegram-бота для консультаций клиентов косметологической клиники

![Изображение](http://www.plantuml.com/plantuml/png/lLH1IiH04BpFA-Oix0ToaFs7I13ScthGU18XxeAN5GzwyAPVc4GZuyQT_KBrZwo91ZL4PqB4Mr9TtLLKTp8zoVQEizF30wNubCqqRb73eCGQ3bMALrHOoxK-KrhlREtgoMHRunxFi7Y28SjwLYbB572ImwJisyWbSQjqDFLzxWDH9nSKTJANF6rCb1wIENsy967AQ4rPyAMM1HwJtug3TMxQMieH6rHDpQ26RQoR94nHv-sMWZ5qzaNGeV2-QBbgxVP55yKSCZKX4SK7Ml-PUF-PKkoEy4foMJANg-_DjZ_0pcOZeklSGOWpoF5dsnU_uTk8SirEpySAfdyCir9wLFje_Uwz_Alt-3tz_8bEPqVx_eVw1W00)

Код представлен ниже:
```
@startuml

state Главное_меню {
  [*] --> Ожидание_выбора_опции
  Ожидание_выбора_опции --> Просмотр_новостей: Просмотр_новостей
  Ожидание_выбора_опции --> Просмотр_услуг: Просмотр_услуг
  Ожидание_выбора_опции --> Выбор_специалиста: Выбор_специалиста
}

state Просмотр_новостей {
  [*] --> Отображение_новостей
  Отображение_новостей --> Отображение_новостей: Обновление_новостей
  Отображение_новостей --> Главное_меню: Закрыть_новости
}

state Просмотр_услуг {
  [*] --> Отображение_услуг
  Отображение_услуг --> Главное_меню: Закрыть_услуги
}

state Выбор_специалиста {
  [*] --> Отображение_списка_специалистов
  Отображение_списка_специалистов --> Отображение_списка_специалистов: Обновление_списка_специалистов
  Отображение_списка_специалистов --> Главное_меню: Закрыть_специалиста
}
@enduml
```

## Диаграмма классов ##

Диаграмма классов представляет различные классы и их взаимосвязи в Telegram-боте для консультаций клиентов косметологической клиники. К нему относятся классы ТелеграмБот, Новость, Услуга и Специалист, а также их атрибуты и методы. Telegram-бот имеет ассоциации с новостями, услугами и специалистами, что позволяет пользователям взаимодействовать с ними с помощью методов бота.

Диаграмма классов Telegram-бота для консультаций клиентов косметологической клиники

![Изображение](http://www.plantuml.com/plantuml/png/bLJ1IiD05BpdA_QeI7-WYFHNYlKWL0LRlOZGjA272k99BnLQVs1jNLsQPls5UN_asovPaiq6OgypysRclMrwet7_UdnpCKoIqs5_D19OGI63meOcaDZX1OQcuYuH_EiWXy4QXbAQGdS5blY5fXG6ssCiu45wEd4AcZ6QqGoREl_3Gx9WfumhUe26H0Qz7pKFTSiwoUcF660697uWROXo9EY3mwwulJeVnBcbE25pJNDyqiJnOlQGSKKucMQUT-ytNbcRtpIdmeQHpA7OsYqmO-9IEnOxAsojCaHzG_QbH-XzZjTm9gTferiLBZM-Rr4-PkcrsEsk8P53GyKQmBZBUawRF8lgt9OjtgjEpLrY5_QTD7Rq72WZRvVzykAchTAzsRajcooRd6AT4Fz7Tph1o-iAIc7m1SMyR-lKBAsS-p_2w6uZ0vBUsUN0VfR-0000)

Код представлен ниже:
```
@startuml

class ТелеграмБот {
    -новости: Список<Новость>
    -услуги: Список<Услуга>
    -специалисты: Список<Специалист>
    +показатьНовости(): void
    +показатьУслуги(): void
    +выбратьСпециалиста(): void
    +выбратьУслугу(): void
}

class Новость {
    -заголовок: Строка
    -текст: Строка
    +получитьЗаголовок(): Строка
    +получитьТекст(): Строка
}

class Услуга {
    -название: Строка
    -описание: Строка
    +получитьНазвание(): Строка
    +получитьОписание(): Строка
}

class Специалист {
    -имя: Строка
    -специальность: Строка
    +получитьИмя(): Строка
    +получитьСпециальность(): Строка
}

ТелеграмБот -- Новость: содержит
ТелеграмБот -- Услуга: содержит
ТелеграмБот -- Специалист: содержит

@enduml
```

## Диаграмма последовательности ##

Диаграмма последовательности изображает взаимодействие между клиентом, Telegram-ботом и косметологической клиникой. Она показывает, как клиент взаимодействует с ботом для просмотра новостей, услуг, специалистов и совершения выбора, а бот общается с клиникой для получения соответствующей информации.

Диаграмма последовательности Telegram-бота для консультаций клиентов косметологической клиники

![Изображение](http://www.plantuml.com/plantuml/png/jLLTQl9057tFAWRVtS3ty25r2zr0q221c8XE2ttpfnHAImjzwLkxXHX96pKTjt1cHxqpWyOQfss29OWpuPvpxhdtG5eZxWxvHJzmt0wFXgmT-5x8dG6zz3l-m0qvQvnxWTSRkdrs5l46SqVqVr3HZaPzZqT1rBjI3A7VqNNcw3Y6b3N_A-G_XcV4sCYPd635C8UGKyHAtxzqkQVPwLUKlq9WHP1tn78gxnbXnyYG8ANhXC1qmWSz0YaZKa7FNDxgbndIBPdkGlFLXnzjPu4rNHCO1kGAAHzAhf_adJOxDWO4IUNAEvrZfi49X6uenR8OXnbYqOMwxMQeQSfWKyMQE-qNEJM6sK6vV4IEpEbwTZtZcXZqNAXPl6rdKrQkP5f7O2rdM5IoIw0DCfMUhnpVkeROnmda-yYQzgsTsATG526hjkECGdMjE90ZbZTqpnYPGaBSfY-JuUM-HlfJ5CgijCLVyDOUMKqVrOAbzv9gyXXhjI7TIr8_PZR6og6py9meWZPs-_IEGk8_YQR5VisGLb0uSLnhAvEaq_B2hlhSVW80)

Код представлен ниже:
```
@startuml
actor Client
participant "Telegram Bot" as Bot
participant "Cosmetology Clinic" as Clinic

Client -> Bot: Запуск бота
activate Bot
Bot -> Bot: Показать приветственное сообщение
Bot -> Client: Приветственное сообщение
Bot -> Client: Показать главное меню
Client -> Bot: Выбор просмотра новостей
activate Clinic
Bot -> Clinic: Запрос новостей
Clinic --> Bot: Ответ с новостями
deactivate Clinic
Bot -> Client: Отображение новостей
Client -> Bot: Выбор просмотра услуг
activate Clinic
Bot -> Clinic: Запрос списка услуг
Clinic --> Bot: Ответ со списком услуг
deactivate Clinic
Bot -> Client: Отображение списка услуг
Client -> Bot: Выбор услуги
activate Clinic
Bot -> Clinic: Запрос информации о выбранной услуге
Clinic --> Bot: Ответ с информацией о выбранной услуге
deactivate Clinic
Bot -> Client: Отображение информации о выбранной услуге
Client -> Bot: Выбор просмотра специалистов
activate Clinic
Bot -> Clinic: Запрос списка специалистов
Clinic --> Bot: Ответ со списком специалистов
deactivate Clinic
Bot -> Client: Отображение списка специалистов
Client -> Bot: Выбор специалиста
activate Clinic
Bot -> Clinic: Запрос информации о выбранном специалисте
Clinic --> Bot: Ответ с информацией о выбранном специалисте
deactivate Clinic
Bot -> Client: Отображение информации о выбранном специалисте
deactivate Bot
@enduml

```

## Диаграмма деятельности ##

Диаграмма деятельности отображает последовательность действий в Telegram-боте для консультаций клиентов косметологической клиники. Она начинается с приветственного сообщения, а затем, в зависимости от ввода клиента, либо показывает список новостей, услуг, специалистов, либо завершает сеанс

Диаграмма деятельности Telegram-бота для консультаций клиентов косметологической клиники

![Изображение](http://www.plantuml.com/plantuml/png/dP91JW9144NtVOfUoXLa8LSn4I89ed76FGnHOdJfYeHuXMPCnv5nYYkykf5Lib0J5-9gVbNgl_ydwK5HdbwNDnUJy2d2CMkIBacqID_6PvtHK9ErqhbMhkZe47BKEOAmqNjysP3xOJoAHwneVQBJAkejealtHtO64tEz8rgPTkXZT1erudoQaruipuTJepoHUY56wu2m9V5ASeFdxcWydUrFT-Qj7uQJOlYF6hgmLQiBNWulyUNzGtoj3snqzfsJzOw6v0R_3zB11NwZ2FM-Zc7Mdhq7hH0wFtPN9j7PDzdbz6my2aLvUHK6flrHV000)

Код представлен ниже:
```
@startuml
start
:Начало;
:Приветственное сообщение;
if (Клиент хочет просмотреть новости?) then (Да)
  :Показать список новостей;
elseif (Клиент хочет просмотреть услуги?) then (Да)
  :Показать список услуг;
elseif (Клиент хочет выбрать специалиста?) then (Да)
  :Показать список специалистов;
else (Нет)
  :Конец сеанса;
endif
stop
@enduml

```
