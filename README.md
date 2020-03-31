# Формула для гугл таблиць, яка повертає архівний курсу НБУ валюти на задану дату:

=IMPORTXML(CONCATENATE("https://bank.gov.ua/markets/exchangerates/?date=";TO_TEXT(A2);"&period=daily"); "//td[text()[contains(.,'USD')]]/../td[5]/text()")

Де, 
A2 - дата в форматі ДД.ММ.РРРР (наприклад 26.03.2020)
USD - валюта в форматі XXX (наприклад USD, EUR, PLN)
**
**
**
**
**
P.S. Якщо ви хочите привести кількість одиниць валюти до 1, то використовуйте формулу:

=IMPORTXML(CONCATENATE("https://bank.gov.ua/markets/exchangerates/?date=";TO_TEXT(B2);"&period=daily"); "//td[text()[contains(.,'USD')]]/../td[5]/text()")/IMPORTXML(CONCATENATE("https://bank.gov.ua/markets/exchangerates/?date=";TO_TEXT(B2);"&period=daily"); "//td[text()[contains(.,'USD')]]/../td[3]/text()")
