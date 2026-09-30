# mywl — живые подписки для белых списков

Обновляется автоматически каждые ~30 минут
сервера проходят проверку IP по CIDR-спискам белых списков

## Подписки (добавлять ссылку в клиент → Подписки)

| Ссылка | Название в Happ | Что внутри |
|---|---|---|
| https://raw.githubusercontent.com/maffloppe/mywl/main/sub/test/base64.txt | wl-ekb Все конфиги | все конфиги |
| https://raw.githubusercontent.com/maffloppe/mywl/main/sub/bs/base64.txt | Белые Списки — все операторы | только IP из белых списков |
| https://raw.githubusercontent.com/maffloppe/mywl/main/sub/mts/base64.txt | МТС Белые Списки | под МТС |
| https://raw.githubusercontent.com/maffloppe/mywl/main/sub/megafon/base64.txt | МегаФон Белые Списки | под МегаФон |
| https://raw.githubusercontent.com/maffloppe/mywl/main/sub/beeline/base64.txt | Билайн Белые Списки | под Билайн |
| https://raw.githubusercontent.com/maffloppe/mywl/main/sub/t2/base64.txt | T2 Белые Списки | под T2 |
| https://raw.githubusercontent.com/maffloppe/mywl/main/sub/motiv/base64.txt | Мотив Белые Списки | под Мотив |

## Имена конфигов

- `5G/LTE 🇸🇪 Швеция 1` — IP сервера в белых списках, должен работать в шатдаун;
- `Wi-Fi 🇩🇪 Германия 3` — работает без режима белых списков;
- `5G/LTE 🇫🇮 Финляндия 2 + Телеграм` — проверено: через сервер открывается Telegram

## Пуш-уведомления

Приложение ntfy → топик `wl-ekb-8k2fjq7mzn4v`.

## Какой VPS брать, чтобы попасть в белые списки

Хостинги, чьи IP-диапазоны проходят БС (по данным RKP, ASN):

| Хостинг | ASN |
|---|---|
| Cloud.ru | AS208677 |
| Яндекс.Облако | AS200350, AS215013 |
| VK Cloud | AS47764, AS28709 |
| Selectel | AS50340, AS49505 |
| Timeweb | AS9123 |
| Beget | AS198610 |
| EdgeCenter | AS210756 |
| DDOS-GUARD | AS57724 |
| SpaceWeb | AS44112 |
| Fornex | AS48018 |
| Облачные сегменты операторов | МТС AS8359/60490/209024, МегаФон AS31133/202804/8263, Vimpelcom AS3216/8350, Ростелеком AS25490/12389/8675 |

Полный список — 51 ASN (RKP `wl_hostings.txt`), конвертируется в CIDR скриптом
`as-to-cidr.py` (RIPEstat). Перед арендой проверяй IP:
`check-ip-in-wl.py` (CIDR + ASN-префиксы + свой накопленный список).
Схема «VPS в БС»: российское облако как транзит → туннель на зарубежный выход.
