# MTProxy-install

Установка официального MTProxy одной командой (Ubuntu/Debian)

## 🚀 Быстрый старт

```bash
curl -fsSL -o /tmp/install-mtproxy.sh https://raw.githubusercontent.com/Nikita-admin/MTProxy-install/main/install-mtproxy.sh && sudo PORT=443 WORKERS=1 bash /tmp/install-mtproxy.sh
```

---

## ⚙️ Параметры

Можно управлять через переменные окружения:

```bash
PORT=443        # Порт MTProxy
WORKERS=1       # Количество воркеров
```

Пример:

```bash
curl -fsSL https://raw.githubusercontent.com/Nikita-admin/MTProxy-install/main/install-mtproxy.sh | sudo PORT=8443 WORKERS=2 bash
```

---

## 📦 Что делает скрипт

- Устанавливает зависимости
- Качает и собирает официальный MTProxy
- Создаёт пользователя `mtproxy`
- Генерирует secret
- Настраивает systemd сервис
- Включает автозапуск
- Добавляет автообновление конфигурации Telegram (раз в день)

---

## 🔗 После установки

Скрипт выведет:

- `tg://` ссылку
- `https://t.me/proxy` ссылку
- client secret

---

## 📊 Проверка работы

Статус сервиса:

```bash
systemctl status mtproxy
```

Локальная статистика:

```bash
curl http://127.0.0.1:8888/stats
```

---

## 🔄 Управление

Перезапуск:

```bash
systemctl restart mtproxy
```

Остановка:

```bash
systemctl stop mtproxy
```

---

## ⚠️ Требования

- Ubuntu / Debian
- Root доступ
- Открытый порт (по умолчанию 443)
