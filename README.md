# google_spreadsheet_UA_exchange_rate
Формула для гугл таблиць, яка повертає архівний курсу НБУ валюти на задану дату:

=IMPORTXML(CONCATENATE("https://bank.gov.ua/markets/exchangerates/?date=";TO_TEXT(A2);"&period=daily"); "//td[text()[contains(.,'USD')]]/../td[5]/text()")

Де, 
A2 - дата в форматі ДД.ММ.РРРР (наприклад 26.03.2020)
USD - валюта в форматі XXX (наприклад USD, EUR, PLN)
