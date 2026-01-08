# Vector Ansible Role

Ansible роль для установки и настройки Vector - агента сбора логов.

## Требования

Для работы с этой ролью и тестированием через Molecule, нам потребуется установить следующие зависимости:

### Python зависимости

Установите необходимые Python пакеты:

```bash
pip install -r requirements.txt
```

### Системные зависимости

Так как для роли требуется дёргать systemctl, для запуска тестов необходим Podman:

**Ubuntu/Debian:**
```bash
```

**CentOS/RHEL/Fedora:**
```bash
```

## Использование Molecule

После установки зависимостей вы можете запускать тесты Molecule:

### Тестирование с Podman (по умолчанию)

```bash
molecule create -s default
molecule converge -s default
molecule verify -s default
molecule destroy -s default
```

Или запустить все этапы тестирования последовательно:

```bash
molecule test -s default
```

## Структура роли

- `tasks/` - Основные задачи Ansible
- `handlers/` - Обработчики событий
- `templates/` - Шаблоны конфигурационных файлов
- `files/` - Статические файлы
- `defaults/` - Переменные по умолчанию
- `vars/` - Внутренние переменные роли
- `meta/` - Метаданные роли
- `molecule/` - Тесты Molecule

## Параметры роли

Основные параметры роли определены в `defaults/main.yml`:

- `vector_version` - Версия Vector для установки
- `vector_config` - Конфигурация Vector в формате YAML
- `vector_service_enabled` - Включен ли сервис Vector при загрузке системы
- `vector_service_state` - Состояние сервиса Vector (started, stopped, etc.)

## Лицензия

MIT

## Автор

Arthur Politiko
