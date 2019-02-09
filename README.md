# RozhkovAndrew_infra
RozhkovAndrew Infra repository
## ДЗ № 5 "Знакомство с облачной инфраструктурой"
### Подключение к удалённой машине someinternalhost в одну команду
ssh -At andrew93pav@35.210.131.244 ssh 10.132.0.3

`-t` - ключ для подключения псевдотерминала
### Дополнительное задание: подключение из консоли при помощи команды вида `ssh someinternalhost` 
Для подключения по алиасу `someinternalhost`, необходимо добавить в файл `~/.ssh/config` следующие строки:

Host bastion
  Hostname 35.210.131.244
  User andrew93pav
Host someinternalhost
  ProxyCommand ssh bastion -W 10.132.0.3:22
  User andrew93pav
  
`-W` - ключ создания туннеля
