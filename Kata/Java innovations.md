---
tags:
  - kata
  - java
  - core
---
## Какие нововведения появились в java 8?
- Методы интерфейсов по умолчанию;
- Лямбда-выражения;
- Функциональные интерфейсы;
- Ссылки на методы и конструкторы;
- Повторяемые аннотации;
- Аннотации на типы данных;
- Рефлексия для параметров методов;
- Stream API для работы с коллекциями;
- Параллельная сортировка массивов;
- Новое API для работы с датами и временем;
- Новый движок JavaScript Nashorn;
- Добавлено несколько новых классов для потокобезопасной работы;
- Добавлен новый API для Calendar и Locale;
- Добавлена поддержка Unicode 6.2.0;
- Добавлен стандартный класс для работы с Base64;
- Добавлена поддержка беззнаковой арифметики;
- Улучшена производительность конструктора `java.lang.String(byte[], *)` и метода `java.lang.String.getBytes()`;
- Новая реализация AccessController.doPrivileged, позволяющая устанавливать подмножество привилегий без необходимости проверки всех остальных уровней доступа;
- Password-based алгоритмы стали более устойчивыми;
- Добавлена поддержка SSL/TLS Server Name Indication (NSI) в JSSE Server;
- Улучшено хранилище ключей (KeyStore);
- Добавлен алгоритм SHA-224;
- Удален мост JDBC - ODBC;
- Удален PermGen, изменен способ хранения мета-данных классов;
- Возможность создания профилей для платформы Java SE, которые включают в себя не всю платформу целиком, а некоторую ее часть;
- Инструментарий
	- Добавлена утилита jjs для использования JavaScript Nashorn;
	- Команда java может запускать JavaFX приложения;
	- Добавлена утилита jdeps для анализа .class-файлов.

## Нововведения Java8 >> Java 17
- Коллекции получили метод of();
- Optional получил метод ifPresentOrElse()_;_
- Интерфейсы получили private методы;
- Появилась система модулей;
- Появился var - вывод типа локальной переменной;
- Поддержка switch с лямбдами;
- Многострочные строки “””;
- Классы Records (записей), которые помогают упростить задачу написания большого количества шаблонного кода на Java;
- NullPointerExceptions описывают*,* какая _именно_ переменная имела значение NULL;
- Concurrent Mark Sweep (CMS) был удален, и был добавлен сборщик мусора ZGC.
- Nashorn Javascript Engine удален;
- Сопоставление шаблонов для switch;
- Запечатанные (sealed) классы;
- Замена нативного интерфейса Java (JNI);
- Прекращение поддержки диспетчера безопасности(Security Manager);

## Какие новые классы для работы с датами появились в java 8?
- LocalDate – дата без времени и временных зон;
- LocalTime – время без даты и временных зон;
- LocalDateTime – дата и время без временных зон;
- ZonedDateTime – дата и время с временной зоной; 
- DateTimeFormatter – форматирует даты в строки и наоборот, только для классов java.time;

## Расскажите про класс Optional
**Optional** - новый класс в пакете java.util, является контейнером (оберткой) для значений которая также может безопасно содержать null.
Благодаря опциональным типам можно забыть про проверки на null и NullPointerException.

## Что такое Nashorn?
Nashorn – это движок JavaScript, разрабатываемый на Java компанией Oracle.
Призван дать возможность встраивать код JavaScript в приложения Java. В сравнении с Rhino, который поддерживается Mozilla Foundation, Nashorn обеспечивает от 2 до 10 раз более высокую производительность, так как он компилирует код и передает байт-код виртуальной машине Java непосредственно в памяти.
Nashorn умеет компилировать код JavaScript и генерировать классы Java, которые загружаются специальным загрузчиком. Так же возможен вызов кода Java прямо из JavaScript.

## Что такое jjs?
jjs это утилита командной строки, которая позволяет исполнять программы на языке JavaScript прямо в консоли.

## Какой класс появился в Java 8 для кодирования/декодирования данных?
`public class java.util.Base64`
## Как создать Base64 кодировщик и декодировщик?
`Base64.getEncoder` `Base64.getDecoder`

## Какие дополнительные методы для работы с ассоциативными массивами (maps) появились в Java 8?
- `putIfAbsent()` добавляет пару «ключ-значение», только если ключ отсутствовал: `map.putIfAbsent("a", "Aa");`
- `forEach()` принимает функцию, которая производит операцию над каждым элементом: `map.forEach((k, v) -> System.out.println(v));`
- `compute()` создаёт или обновляет текущее значение на полученное в результате вычисления (возможно использовать ключ и текущее значение):  `map.compute("a", (k, v) -> String.valueOf(k).concat(v)); //["a", "aAa"];`
- `computeIfPresent()` если ключ существует, обновляет текущее значение на полученное в результате вычисления (возможно использовать ключ и текущее значение): `map.computeIfPresent("a", (k, v) -> k.concat(v));`
- `computeIfAbsent()` если ключ отсутствует, создаёт его со значением, которое вычисляется (возможно использовать ключ): ` map.computeIfAbsent("a", k -> "A".concat(k)); //["a","Aa"];`
- `getOrDefault()` в случае отсутствия ключа, возвращает переданное значение по умолчанию:  `map.getOrDefault("a", "not found");`
- `merge()` принимает ключ, значение и функцию, которая объединяет передаваемое и текущее значения. Если под заданным ключом значение отсутствует, то записывает туда передаваемое значение.
- `map.remove(key, value)` - Если такое ключ-значение есть в map, то удаляем.

## Что такое LocalDateTime?
LocalDateTime объединяет вместе LocaleDate и LocalTime, содержит дату и время в календарной системе ISO-8601 без привязки к часовому поясу. Время хранится с точностью до наносекунды. Содержит множество удобных методов, таких как plusMinutes, plusHours, isAfter, toSecondOfDay и т.д.

## Что такое ZonedDateTime?
java.time.ZonedDateTime — аналог java.util.Calendar, класс с самым полным объемом информации о временном контексте в календарной системе ISO-8601. Включает временную зону, поэтому все операции с временными сдвигами этот класс проводит с её учётом.