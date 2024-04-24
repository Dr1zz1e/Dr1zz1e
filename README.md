# Содержимое
- [[#Wigglererer`s site for trial pentest|Wigglererer`s site for trial pentest]]
	- [[#Wigglererer`s site for trial pentest#Оценка|Оценка]]
	- [[#Wigglererer`s site for trial pentest#Описание|Описание]]
	- [[#Wigglererer`s site for trial pentest#POC (Proof of Concept)|POC (Proof of Concept)]]
	- [[#Wigglererer`s site for trial pentest#Рекомендации по устранению|Рекомендации по устранению]]

# Область тестирования

| IP/домен     | Порт | URL                                 |                  Сервис                  |
| ------------ | ---- | ----------------------------------- |	------------------------------------   |
| 127.0.0.1    | 4949 |  https://dr1zz1e.pythonanywhere.com/|	Wigglererer`s site for trial pentest   |

# Найденные уязвимости

- SQL injection (SQLi) 

### Оценка 

- SQLi: Базовая оценка (BS): 7.1

### Описание
> Веб сайты могут являться системами взаимодействия с базами данных и доступ к БД должен быть обязательно конфиденциальным, однако данный сайт имеет уязвимость позволяющуюю всем просматривать содержимое, в том числе и пароди от аккаунтов.

### POC (Proof of Concept)
```shell
'UNION SELECT password from users --
```
(скриншот получаемых паролей из базы данных можно увидеть по ссылке: https://drive.google.com/drive/folders/1cvKCcxkJuEJ0JDf5lQwpj0oVfJBMhFQU?usp=sharing)

### Рекомендации по устранению
Добавить проверку запросов на ключевые слова по типу "UNION", "SELECT" и "ORDER (BY)"

P.S
# Proof of concept screenshots: https://drive.google.com/drive/folders/1cvKCcxkJuEJ0JDf5lQwpj0oVfJBMhFQU?usp=sharing
