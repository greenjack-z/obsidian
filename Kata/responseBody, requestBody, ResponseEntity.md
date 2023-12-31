Аннотация [@ResponseBody] ставится на методы, которые работают с данными, а не с моделями. Ее не требуется указывать явно, если используется `@RestController`.
Обычные методы возвращают `Model`, а методы аннотированные `@ResponseBody` возвращают объекты, которые конвертируются в медиа-файлы с помощью `HttpMessageConverter`.

Вы можете использовать аннотацию [@RequestBody] на параметре метода, для того чтобы тело запроса конвертировалось в этот параметр.

ResponseEntity - это [специальный класс](https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/http/ResponseEntity.html), который представляет http-ответ. Он содержит тело ответа, код состояния, заголовки. Мы можем использовать его для более тонкой настройки http-ответа.