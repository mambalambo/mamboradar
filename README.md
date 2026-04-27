# MamboRadar 🚀

[English](#english) | [Русский](#русский)

---

<a id="english"></a>
## 🇬🇧 English

### What is MamboRadar?
**MamboRadar** is a blazing-fast, fully automated, and asynchronous Minecraft server scanner written in pure Python. It is designed to scan thousands of ports across multiple hosts to find active Minecraft servers without relying on heavy external tools.

### How it Works
1. **Target Loading**: The script reads target domains or IP addresses from `pubs.txt`.
2. **DNS Resolution**: Each host is resolved to its corresponding IP address.
3. **High-Speed TCP Pinging**: It scans ports ranging from `10000` to `65535` in massive asynchronous batches (1000 ports per batch) using a quick TCP connection test (1-second timeout).
4. **Server Verification**: When an open port is detected, the script instantly pings the server using the `mcstatus` library to verify it's a valid Minecraft server.
5. **Data Extraction**: It extracts the server version, current/max players, calculates the exact ping, and cleans up the MOTD.
6. **Logging**: All found servers are automatically written in real-time to `found.txt`.

### How to Use

#### 1. Prerequisites
Make sure you have Python 3.7+ installed. You only need to install one external library:
```bash
pip install mcstatus
```

#### 2. Targets (Ready to Go)
The target hosts are already pre-configured in the `pubs.txt` file. You don't need to manually configure them-the list is prepared and ready for execution.

#### 3. Run the Scanner
Start the script:
```bash
python main.py
```

#### 4. View Results
Sit back and relax! The scanner will output progress to the console and continuously save any discovered servers directly into `found.txt` in the following format:
`IP:PORT | Version | Players | Ping | MOTD`

---

<a id="русский"></a>
## 🇷🇺 Русский

### Что такое MamboRadar?
**MamboRadar** - это невероятно быстрый, полностью автоматизированный асинхронный сканер Minecraft серверов, написанный на чистом Python. Он предназначен для сканирования тысяч портов на множестве хостов с целью поиска активных серверов без использования тяжелых внешних инструментов.

### Как это работает
1. **Загрузка целей**: Скрипт считывает целевые домены или IP-адреса из файла `pubs.txt`.
2. **DNS Резолвинг**: Каждый хост преобразуется в соответствующий IP-адрес.
3. **Быстрый TCP-пинг**: Скрипт сканирует порты в диапазоне от `10000` до `65535` огромными асинхронными пачками (по 1000 портов за раз), используя быстрый тест TCP-соединения (таймаут 1 секунда).
4. **Проверка сервера**: Как только обнаруживается открытый порт, скрипт мгновенно опрашивает его с помощью библиотеки `mcstatus`, чтобы убедиться, что это действительно Minecraft сервер.
5. **Сбор данных**: Извлекается версия сервера, количество игроков (текущее/максимальное), высчитывается точный пинг и очищается MOTD (описание) от лишнего мусора.
6. **Логирование**: Все найденные серверы автоматически и в реальном времени записываются в файл `found.txt`.

### Как использовать

#### 1. Требования
Убедитесь, что у вас установлен Python 3.7+. Вам нужно установить только одну внешнюю библиотеку:
```bash
pip install mcstatus
```

#### 2. Цели (уже готовы)
Целевые хосты уже заранее настроены в файле `pubs.txt`. Вам не нужно ничего настраивать вручную - список полностью готов к запуску.

#### 3. Запуск сканера
Запустите скрипт:
```bash
python main.py
```

#### 4. Результаты
Скрипт будет выводить в консоль информацию о начале сканирования каждого хоста, а все успешно найденные серверы будут моментально сохраняться в файл `found.txt` в удобном формате:
`IP:PORT | Версия | Игроки | Пинг | MOTD`
