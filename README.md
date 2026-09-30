# 🔐 Password Manager for Linux

Учебный проект по курсу **"Linux: основы процессов и потоков"**. 
Менеджер паролей с хранением в SQLite, шифрованием через base64, генерацией паролей, логированием операций и резервным копированием.

---

## ✨ Возможности

- 🗄️ Хранение паролей в базе данных **SQLite** (`passwords.db`)
- 🔒 Простое кодирование паролей через **base64**
- 🎲 Генерация паролей двух уровней сложности:
  - **Простой**: 8 символов (только буквы)
  - **Сложный**: 12 символов (буквы + цифры + спецсимволы)
- 📊 Логирование операций (ADD / GET / DEL) в `usage.log`
- 💾 Резервное копирование базы в `/home/security/backups/`
- 🛡️ Разграничение прав доступа через группу `security`

---

## 📦 Технологии

- **Python 3** ( `sqlite3` `secrets` `base64` `tarfile` `shutil`)
- **Bash**
- **Ubuntu** (VirtualBox)

---

## 🚀 Установка и запуск

### 1. Клонировать репозиторий

git clone https://github.com/your-username/password-manager-linux.git
cd password-manager-linux

### 2. Настроить окружение

sudo groupadd security

sudo mkdir -p /home/security/backups

sudo chown :security /home/security

sudo chmod 770 /home/security

sudo chmod 770 /home/security/backups

### 3. Запустить менеджер паролей

python3 password_manager.py add google user --generate

python3 password_manager.py get google

python3 password_manager.py list

python3 password_manager.py del google

## 🛠️ Команды

add <service> <login> <password>	Добавить запись со своим паролем

add <service> <login> --generate	Добавить со сгенерированным сложным паролем

add <service> <login> --generate-simple	Добавить со сгенерированным простым паролем

list	Показать список сервисов

get <service>	Показать логин и пароль

del <service>	Удалить запись

backup	Создать резервную копию базы

stats	Показать статистику операций

## Примеры

python3 password_manager.py add github user --generate

python3 password_manager.py get github

python3 password_manager.py list

python3 password_manager.py backup

python3 password_manager.py stats

## 📂 Структура проекта

├── password_manager.py      # Основной скрипт

├── password_generator.py    # Генератор паролей

├── usage_monitor.py         # Мониторинг операций

├── archive.py               # Архивация passwords.txt

├── passwords.db             # База данных (создаётся автоматически)

├── usage.log                # Лог операций

└── README.md


## 👤 Автор
user — Федулова ВА

## 📄 Лицензия
Проект создан в учебных целях.
