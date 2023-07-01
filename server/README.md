Включить сбор логов auditd (см. /etc/filebeat/modules.d/)
---
```
filebeat modules enable auditd
```

Аудит всех команд пользователя root
---
```
auditctl -a exit,always -F arch=b64 -F uid=0 -S execve -k auditcmd
auditctl -l
```
>-a always,exit -F arch=b64 -S execve -F uid=0 -F key=auditcmd
