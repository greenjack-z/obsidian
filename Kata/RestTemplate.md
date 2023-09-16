RestTemplate это специальный _клиент для отправки запросов в Spring_. Он предоставляет удобные API для легкого вызова конечных точек REST’а в одну строку.

Основные методы:  
  
**getForEntity** - выполняет запрос GET и возвращает объект ResponseEntity;  
  
**getForObject** - аналогично getForEntity, но возвращает ресурс напрямую;  
  
**exchange** - выполняет указанный метод HTTP, такой как GET, POST, PUT и т. д., и возвращает объект ResponseEntity;  
  
execute - аналогичен exchange методу, но требует дополнительных параметров: RequestCallback и ResultSetExtractor;  
  
**headForHeaders** - выполняет запрос HEAD и возвращает все заголовки;  
  
**optionsForAllow** - выполняет запрос OPTIONS и использует заголовок Allow;  
  
**delete** - удаляет ресурсы по указанному URL-адресу с помощью метода HTTP DELETE;  
  
**put** - обновляет ресурс для заданного URL-адреса с помощью метода HTTP PUT;  
  
**postForObject** - создает новый запрос с использованием метода HTTP POST и возвращает сущность;  
  
**postForLocation** - создает новый запрос с использованием метода HTTP POST и возвращает его расположение; 