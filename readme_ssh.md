<h1 align="center">Универсальный менеджер для обхода блокировок на OpenWrt</h1>

<div align="center">

![Platform](https://img.shields.io/badge/Platform-OpenWrt-orange)
![Architecture](https://img.shields.io/badge/Architecture-All%20(OpenWrt)-yellow)
![Script](https://img.shields.io/badge/Script-sh-informational)
![Status](https://img.shields.io/badge/Status-Active-success)

</div>

---

# 💡  **Рекомендую Zapret Manager WEB + LuCI**
>[!NOTE]
> Удобнее всего управлять всем из браузера!
> 
> Установите панель один раз — в SSH выполните команду:
> ```
> wget -O /tmp/ZapretManager_LuCI.sh https://raw.githubusercontent.com/StressOzz/Zapret-Manager/main/ZapretManager_LuCI.sh
> sh /tmp/ZapretManager_LuCI.sh
> ```
> и откройте ссылку в брузере (например, `http://192.168.1.1:7788`) на компьютере или телефоне
> также, в LuCI появится пункт **Zapret Manager**
>
> Там всё то же самое, что в SSH, но нагляднее: стратегии, YouTube / Discord / игры, Steer, ByeTube, Mixomo, DNS over HTTPS — с живыми статусами, логами и без ввода команд. SSH-меню остаётся для быстрых действий и работает с панелью заодно: изменения в одном месте сразу видны в другом.


---

# Оглавление
- [Возможности](#-возможности)
- [Подготовка системы](#-подготовка-системы)
- [Запуск менеджера](#-запуск-менеджера)
- [Быстрый старт](#-быстрый-старт)
- [Настройка Telegram](#-telegram)
- [Cтратегии](#-стратегии)
- [Mixomo](#-mixomo)
- [Благодарности](#благодарности)

---

## 🔹 Возможности

### Zapret Manager позволяет:

- Установить **Zapret** последней версии
- Выбрать стратегию для установки **v1-v9**
- Выбрать и установить стратегию от **Flowseal**
- Протестировать стратегии **v1-v9** и **Flowseal**
- Подобрать стратегию для **YouTube**
- Сделать резервную копию настроек **Zapret** 
- Включить стратегию для игр **Battlefield 6**, **Apex Legend**, **Roblox** и других...
- Установить скрипт для **Discord**
- Включить обход Финских **IP** для **Discord**
- Выбрать стратегию для **discord.media**
- Установить **DoH** (**DNS over HTTPS**) и выбрать **DNS**-сервер
- Получить доступ к **Zapret Manager** из браузера
- Включить блокировку **QUIC** (порты 80,443)
- Включить или выключить **IP** в **hosts**
- Открыть доступ к **AI** сервисам без **VPN**
- Разблокировать **Telegram WEB**, **rutor.info**, **ntc.party**, **lib.rus.ec**, **Instagram***
- Разблокировать разрешение на **Twitch**
- Сменить источник (выбрать зеркало) для пакетов **OpenWRT**
- Установить различные **TG WS Proxy** для **Telegram**
- Установить [**NetShift**](https://github.com/yandexru45/netshift)
- Установить [**Mixomo**](https://github.com/Internet-Helper/mixomo-openwrt)
- Установить [**splify**](https://github.com/xyzmean/splify)
- Установить [**Zapret2 Routerich Edition**](https://github.com/routerich)
- Интегрировать VPN-подписку в **NetShift** и **Mixomo**
- Сгенерировать **WARP** и интегрировать его в **Mixomo**
- Запустить автоподбор стратегий по расписанию

---

## 🔹 Подготовка системы

> [!IMPORTANT]
>для работы некоторых стратегий, в терминале Windows необходимо один раз выполнить:
>```
>netsh int tcp set global timestamps=enabled
>```
>
>для пользователей Linux:
>```
>sysctl -w net.ipv4.tcp_timestamps=1
>```

- Если у Вас установлен **ByeDPI** или **youtubeUnblock** скрипт выдаст сообщение.
- Если у Вас включён **Flow offloading** скрипт выдаст сообщение и в `Системном меню`, появится пункт **0** - **Применить FIX**.
- [**NetShift** берёт на себя роль DNS-резолвера](https://podkop.net/docs/dns/), поэтому с установленным `DNS over HTTPS` [**NetShift не установится!**](https://podkop.net/docs/install/#nesovmestimost)

---

## 🔹 Запуск менеджера в LuCI или в браузере

Для запуска **Zapret Manager** в **LuСI** или **в браузере**, выполните в **SSH**
```
wget -O /tmp/ZapretManager_LuCI.sh https://raw.githubusercontent.com/StressOzz/Zapret-Manager/main/ZapretManager_LuCI.sh
sh /tmp/ZapretManager_LuCI.sh
```
или - запустите основной скрипт → Установить **Zapret Manager для WEB + LuCI**

После установки, скрипт будет доступен в браузере по ссылке **http://192.168.1.1:7788/** (192.168.1.1 это IP вашего роутера)

в **LuCI** вкладка **Services** → **Zapret Manager**

---

## 🔹 Запуск менеджера

Подключитесь по **SSH** к роутеру и выполните команду:
> [!IMPORTANT]
> Сохраните скрипт и запустите уже файл. Повторно из сети он сам не скачивается, сторонние зеркала GitHub не используются:
```
wget -O /tmp/Zapret-Manager.sh https://raw.githubusercontent.com/StressOzz/Zapret-Manager/main/Zapret-Manager.sh
sh /tmp/Zapret-Manager.sh
```

---

После запуска скрипта по команде выше, скрипт можно запускать в **SSH** командой:
```
zms
```

---

## 🔹 Запуск менеджера в браузере

- запустите основной скрипт → Системное меню → Активировать доступ к скрипту из браузера

После установки, скрипт будет доступен:
- в браузере по адресу **http://192.168.1.1:7681**

---

## 🔹 Быстрый старт

**Пункт f** - **Удалить → установить → настроить Zapret**

Установка **Zapret** под ключ:
- Удаляет Zapret
- Устанавливает последнюю версию Zapret
- Устанавливает стратегию **v7**
- Устанавливает скрипт **50-stun4all**
- Добавляет в стратегию настройки для игр
- Добавляет домены **Telegram WEB**, **AI**, **rutor.info**, **ntc.party**, **lib.rus.ec**, **Twitch**, **Instagram***  в `hosts`

>⚠️ Использовать только для полной переустановки и настройки Zapret.

## 🔹 Стратегии

Если у Вас не запускается **Youtube** на каком-либо устройстве, то попробуйте подобрать стратегию только для **YouTube**.

В скрипте, в пункте 2, затем 0 - Тестировать стратегии для `YouTube` и Тестировать `v` и `Flowseal` стратегии

- [Cтратегии для Youtube](https://github.com/StressOzz/Zapret-Manager/blob/main/Strategies_For_Youtube.md)
- [Cтратегии используемые в скрипте](https://github.com/StressOzz/Zapret-Manager/blob/main/Strategies.md)

## 🔹 Telegram

В **Telegram Desktop**:
- Настройки **→** Продвинутые настройки **→** Тип соеденения **→** Добавить прокси
- Выберите **SOCKS5** / **MTPROTO**
- В поле **Хост** укажите **IP**, в **Порт** укажите **порт**
- Для **MTPROTO** в **Ключ** укажите **ключ**
- Нажмите Сохранить

В **приложении Telegram**:
- Настройки **→** Данные и память **→** Настройки прокси **→** Добавить прокси
- Выберите **SOCKS5** / **MTPROTO**
- В поле **Сервер** укажите **IP**, в **Порт** укажите **порт**
- Для **MTPROTO** в **Ключ** укажите **ключ**
- Нажмите на галочку в верхнем правом углу

---

## 🔹 Mixomo

- Интегрировать **VPN** подписку в **Mihomo**

   Вставьте ссылку на свою подписку.

   Панель Mihomo слушает только сам роутер: `127.0.0.1:9090`. С других устройств домашней сети этот порт не открывается.
   во вкладке **Прокси** выберите **Сервер для YouTube** и **Сервер для остального трафика** который поёдйт через списки **MagiTrickle**
   
- Сгенерируйте **WARP** 
 
   Для генерации **WARP** через скрипт понадобится установить **[Zapret](https://github.com/StressOzz/Zapret-Manager)**
   
- Интегрируйте **WARP**

   Для интеграции своего **WARP** файла - скиньте его в `/root/WARP.conf`
   
- Зайдите на http://192.168.1.1:8080/ выберите списки, которые Вам нужны, нажмите **Сохранить изменения**

- Можете выбрать и установить панель для управления **Mihomo** - пункт **7**

- Можете включить автоперезапуск **Mihomo** - может помочь при использовании сгенерированных warp

---

## 🔹 Expert mode

В `Системном меню` можно включить **expert mode**, что позволит Вам управлять сразу двумя версиями Zapret...

---

## 🔹 Тест стратегий из **/root/custom_test.txt**

Каждая стратегия должна начинаться со строки **#Название**

Пример содержимого `/root/custom_test.txt`:
```
#Strategy1
--filter-tcp=443
--dpi-desync=fake
. . .
#Strategy2
--filter-tcp=443
--dpi-desync=multidisorder
. . .
```

---

# Благодарности:

- **Zapret** by [*bol-van*](https://github.com/bol-van)
- **Zapret-OpenWrt** by [*remittor*](https://github.com/remittor)
- **Zapret2 Routerich Edition** by [*Routerich*](https://github.com/routerich)
- **Стратегии Flowseal** by [*Flowseal*](https://github.com/Flowseal)
- **NetShift** by [*yandexru45*](https://github.com/yandexru45)
- **splify** - by [*xyzmean*](https://github.com/xyzmean/)
- **Mixomo** by [*Internet Helper*](https://github.com/Internet-Helper)
- **MagiTrickle** by [*Ponywka*](https://github.com/Ponywka)
- **HevSocks5Tunnel** by [*hev*](https://github.com/heiher)
- **AWG OpenWrt** by [*2Grey*](https://github.com/2Grey)
- **TG WS Proxy SOCKS5** by [*byd0mhate*](https://github.com/d0mhate)
- **TG WS Proxy Rust** by [*valnesfjord*](https://github.com/valnesfjord)
- **TG WS Proxy MTProto** by [*spatiumstas*](https://github.com/spatiumstas)
- **ByeDPI-OpenWrt** by [*DPITrickster*](https://github.com/DPITrickster)

---

*принадлежит компании Meta, признанной экстремистской и запрещённой на территории РФ
