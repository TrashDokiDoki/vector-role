# Vector Role

Ansible role для установки и настройки Vector.

## Что делает роль

- создает системного пользователя Vector;
- скачивает и распаковывает Vector;
- создает необходимые каталоги;
- устанавливает конфигурацию из Jinja2-шаблона;
- создает systemd service;
- запускает Vector и добавляет его в автозагрузку.

## Переменные

Основные переменные роли:

```yaml
vector_version: "0.34.0"
vector_install_dir: "/opt/vector"
vector_config_dir: "/etc/vector"
vector_data_dir: "/var/lib/vector"
vector_user: "vector"
vector_group: "vector"
```

## Пример использования

```yaml
---
- name: Install Vector
  hosts: vector
  become: true

  roles:
    - vector_role
```