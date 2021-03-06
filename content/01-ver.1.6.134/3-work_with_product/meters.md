---
slug: "/post6"
title: "Вкладка Счетчики в Личном кабинете"
sort: "03"
---

Вкладка **Счетчики** нужна для работы модуля **АППС**, представляет собой таблицу **Управление показаниями счетчиков**, кнопки **Удалить** и **Экспорт**, **Панель навигации** по таблице и настройку **Строк на странице**.

## Управление показаниями счетчиков содержит:

### Наименование счетчика

В этом поле содержится название счетчика, которое мы получаем из системы 1С ЖКХ.

![Картинка](./images/meters_field_name_meter.png "Поле Наименование счетчика")

#### Тарифов

В этом поле указывается количество тарифов для определенного счетчика. Всего может быть 3 тарифа: первый отвечает за дневное показание счетчика, второй за ночное показание и третий за пиковое.

![Картинка](./images/meters_field_rate.png "Поле Тарифов")

### Разрядов

В этом поле указывается количество разрядов для определенного счетчика.

🛈 Это дополнительный параметр, не влияющий на счетчик.  

![Картинка](./images/meters_field_capacity.png "Поле Разрядов")

### Сервис

В этом поле содержится название сервиса, которое мы получаем из системы 1С.  
Например:  **Горячая вода** или **Холодная вода**.

![Картинка](./images/meters_field_service.png "Поле Сервис")

### Последнее обновление

В этом поле указывается дата последнего приема показаний счетчика, если приема показаний не происходило, то ставится дата создания из системы 1С. Дата указывается в формате:

![Картинка](./images/meters_field_last_update.png "Поле Последнее обновление")

**YYYY-MM-DDTHH:mm:ss.sssZ**, где:

**YYYY-MM-DD** – дата в формате год-месяц-день.  
**T** - разделитель.  
**HH:mm:ss.sss** – время: часы-минуты-секунды-миллисекунды.  
Часть **Z** обозначает временную зону – в формате +-hh:mm, либо символ Z, обозначающий UTC.

🛈 По стандарту её можно не указывать.

Также возможны укороченные варианты, например **YYYY-MM-DD** или **YYYY-MM** или даже только **YYYY**.

### Номер л/с

В этом поле указывается номер лицевого счета,  которое мы получаем из системы 1С. Этот параметр один для вкладки **Лицевые счета**.

🛈 Если лицевой счет будет удален, все счетчики связанные с ним, также удалятся.

![Картинка](./images/meters_field_number_meter.png "Поле Номер л/с")

### Показания 1

В этом поле указывается дневное показание для определенного счетчика, которое мы получаем из системы 1С.

![Картинка](./images/meters_field_coutner_1.png "Поле Показания 1")

🛈 Показание записывается в целом формате без запятых и точек.

Например: 117, 2000.

### Показания 2

В этом поле указывается ночное показание для определенного счетчика, которое мы получаем из системы 1С.

![Картинка](./images/meters_field_coutner_2.png "Поле Показания 2")

🛈 Показание записывается в целом формате без запятых и точек.

Например: 117, 2000.

### Показания 3
В этом поле указывается пиковое показание для определенного счетчика, которое мы получаем из системы 1С.

![Картинка](./images/meters_field_coutner_3.png "Поле Показания 3")

🛈 Показание записывается в целом формате без запятых и точек.

Например: 117, 2000.

### От жильца

Этом поле указывается откуда данные поступили в платформу Kloud.One. При значении **false** данные получены из 1С или загружены вручную. При значении **true** данные получены от абонента.

![Картинка](./images/meters_field_from.png "Поле От жильца")

🛈 После первого приема показаний статус автоматически меняется на **true**.

## Панель Управления по таблице содержит:

### Удалить

При нажатии кнопки **Удалить** выделенная строка удаляется из таблицы Управление показаниями счетчиков.

![Картинка](./images/meters_butt_delete.png "Кнопка Удалить")

Для удаления одной или несколько строк из таблицы, выберите флажок слева от **названия счётчика** и нажмите на кнопку **Удалить**.

### Экспорт (.json)

После нажатия на кнопку **Экспорт (.json)**  данные из таблицы экспортируются в файл **export.json**.

![Картинка](./images/meters_butt_export(json).png "Кнопка Экспорт (.json)")

![Картинка](./images/meters_download_export(json).png "Скачанный файл export.json")

🛈 Экспортируются все данные, которые находятся в таблице **Управление показаниями счетчиков**.


Содержимое  файла  **export.json**:
```
[
    {
        "acc_id": {
            "id": "5f16fb358d0ddc0fd0ea4d62_0505032"
        },
        "name": "Вода",
        "values": 1,
        "capacity": 6,
        "service": "Холодная вода",
        "date": "2020-09-07T00:00:00.000Z",
        "val1": 0,
        "val2": 0,
        "val3": 0,
        "id": "00000001"
    },
    {
        "acc_id": {
            "id": "5f16fb358d0ddc0fd0ea4d62_0505032"
        },
        "name": "Газ",
        "values": 1,
        "capacity": 6,
        "service": "Газовое снабжение",
        "date": "2020-09-07T00:00:00.000Z",
        "val1": 356,
        "val2": 0,
        "val3": 0,
        "id": "00000002"
    }
]
```

## Панель навигации по таблице содержит:

### Вернуться на первую страницу

После нажатия на кнопку **Вернуться на первую страницу**  откроется 1 страница таблицы.

🛈 Тусклая кнопка означает что вы уже на первой странице или таблица имеет всего 1 страницу.

![Картинка](./images/meters_butt_first_page.png "Кнопка Вернуться на первую страницу")

![Картинка](./images/meters_page_88_432.png "Cейчас открыта 88 страница")

![Картинка](./images/meters_page_1_432.png "После нажатия на кнопку открылась 1 страница")

### Кнопка "Вернуться на предыдущую страницу"

После нажатия на кнопку **Вернуться на предыдущую страницу**  откроется предыдущая страница по счету таблицы.

🛈 Тусклая кнопка означает что вы уже на первой странице или таблица всего имеет 1 страницу.

![Картинка](./images/meters_butt_previous_page.png " Кнопка Вернуться на предыдущую страниц")

![Картинка](./images/meters_page_44_432.png "Сейчас открыта 44-я страница")

![Картинка](./images/meters_page_43_432.png "После нажатия на кнопку открылась предыдущая страница")

### Стр.

Поле **Стр.** отображает количество страниц таблицы, этот параметр связан с параметром **Строк на странице**, чем больше строк на странице, тем меньше отображается страниц в таблице.

![Картинка](./images/meters_page_43_432.png "Параметр Стр. 43 из 432 страниц")

### Перейти на следующую страницу

После нажатия на кнопку **Перейти на следующую страницу** откроется следующая страница по счету таблицы.

🛈 Тусклая кнопка означает, что открыта последняя страница или таблица всего имеет 1 страницу.

![Картинка](./images/meters_butt_next_page.png "Кнопка Перейти на следующую страницу")

![Картинка](./images/meters_page_44_432.png "Сейчас открыта 44-я страница")

![Картинка](./images/meters_page_45_432.png "После нажатия на кнопку открылась следующая страница")

### Перейти на последнюю страницу

После нажатия на кнопку **Перейти на последнюю страницу** откроется последняя страница таблицы.

🛈 Тусклая кнопка означает что вы уже на последней странице или таблица всего имеет 1 страницу.

![Картинка](./images/meters_butt_last_page.png "Кнопка Перейти на последнюю страницу")

![Картинка](./images/meters_page_45_432.png "Сейчас открыта 45-я страница")

![Картинка](./images/meters_page_432_432.png "После нажатия на кнопку открывается последняя страница")

### Строк на странице и выпадающий список

Настройка **Строк на странице** отображает количество строк в таблице, из выпадающего списка можем выбрать одно из несколько значений: 10, 20, 50, 100, 200.

🛈 Этот параметр связан с **параметром Стр.**, чем больше строк на странице, тем меньше отображается страниц в таблице.

![Картинка](./images/meters_page_10.png "Настройка Строк на страницев")