# 02: Установка и настройка ansible

## Команды Ansible

```bash
# Чек, что ansible удается соединиться по ssh
ansible testserver -m ping

# модуль command используется по умолчанию
ansible testserver -m command -a uptime
ansible testserver -a uptime

# Кавычки для передачи полной команды
ansible testserver -a "tail /var/log/dmesg"

# С become (sudo)
ansible testserver -ba "tail /var/log/syslog"

# Установка nginx с обновлением кэша пакетного менеджера
ansible testserver -bm package -a "name=nginx update_cache=yes"

# Перезапуск сервиса nginx
ansible testserver -bm service -a "name=nginx state=restarted"
```
