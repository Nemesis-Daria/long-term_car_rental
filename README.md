# long-term_car_rental

**Цель работы**

Проверка гипотез:  
•	Органический трафик не отличается от платного с точки зрения CR (Conversion Rate) в целевые события.  
•	Трафик с мобильных устройств не отличается от трафика с десктопных устройств с точки зрения CR (Conversion Rate) в целевые события.  
•	Трафик из городов присутствия (Москва и область, Санкт-Петербург) не отличается от трафика из иных регионов с точки зрения CR (Conversion Rate) в целевые события.

Ответы на вопросы:  
•	Из каких источников / кампаний / устройств / локаций к нам идёт самый целевой трафик (и с точки зрения объёма трафика, и с точки зрения CR)?  
•	Какие авто пользуются наибольшим спросом? У каких авто самый лучший показатель CR (Conversion Rate) в целевые события?  
•	Стоит ли нам увеличивать своё присутствие в соцсетях и давать там больше рекламы?

**Описание данных**

Таблица GA Sessions:

Одна строка = один визит на сайт.

Описание атрибутов:  
•	session_id — ID визита;  
•	client_id — ID посетителя;  
•	visit_date — дата визита;  
•	visit_time — время визита;  
•	visit_number — порядковый номер визита клиента;  
•	utm_source — канал привлечения;  
•	utm_medium — тип привлечения;  
•	utm_campaign — рекламная кампания;  
•	utm_keyword — ключевое слово;  
•	device_category — тип устройства;  
•	device_os — ОС устройства;  
•	device_brand — марка устройства;  
•	device_model — модель устройства;  
•	device_screen_resolution — разрешение экрана;  
•	device_brand — марка устройства;  
•	device_model — модель устройства;  
•	device_screen_resolution — разрешение экрана;  
•	device_browser — браузер;  
•	geo_country — страна;  
•	geo_city — город.

Таблица GA Hits:

Одна строка = одно событие в рамках одного визита на сайт.

Описание атрибутов:  
•	session_id — ID визита;  
•	hit_date — дата события;  
•	hit_time — время события;  
•	hit_number — порядковый номер события в рамках сессии;  
•	hit_type — тип события;  
•	hit_referer — источник события;  
•	hit_page_path — страница события;  
•	event_category — тип действия;  
•	event_action — действие;  
•	event_label — тег действия;  
•	event_value — значение результата действия.  

**Глоссарий**

**Целевое действие** — события типа «Оставить заявку» и «Заказать звонок» (ga_hits.event_action in ['sub_car_claim_click', 'sub_car_claim_submit_click', 'sub_open_dialog_click', 'sub_custom_question_submit_click', 'sub_call_number_click', 'sub_callback_submit_click', 'sub_submit_success', 'sub_car_request_submit_click']).

**CR (Conversion Rate)** — показатель конверсии из визита (уникальный session_id) в любое целевое действие в рамках одного визита (в случае наличия >1 целевого действия — считать все как одно).

**Органический трафик** — все визиты с ga_sessions.utm_medium in ('organic', 'referral', '(none)').

**Платный трафик** — весь неорганический трафик.

**Информация про марку и модель авто** — содержится в ga_hits.hit_page_path.

**Реклама в социальных сетях** — все визиты с ga_sessions.utm_source in ('QxAxdyPLuQMEcrdZWdWb', 'MvfHsxITijuriZxsqZqt', 'ISrKoXQCxqqYvAZICvjs', IZEXUFLARCUMynmHNBGo', 'PlbkrSYoHuZBWfYjYnfw', 'gVRrcxiDQubJiljoTbGm').

