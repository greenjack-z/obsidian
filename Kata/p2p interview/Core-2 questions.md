---
tags:
  - kata
  - java
  - core
  - core2
---
```dataview
TABLE WITHOUT ID
(length(filter(this.file.tasks.completed, (t) => t = true))) AS ОК,
(length(filter(this.file.tasks.completed, (t) => t = false))) AS Осталось,
(length(this.file.tasks)) AS Всего,
(length(filter(this.file.tasks.completed, (t) => t = true))) / (length(this.file.tasks)) * 100 AS "% OK"
WHERE file.path = this.file.path
```

## Generics
Вопросов в разделе: `= (length(filter(this.file.tasks.section, (h) => meta(h).subpath = "Generics")))`

> [!question]- Что такое дженерики?
> ![[Generics#Generics]]
> - [ ] OK

> [!question]- Для чего нужны дженерики?
> ![[Generics#Why Use Generics?]]
> - [ ] OK

> [!question]- Что такое сырые типы (raw type)?
> ![[Generics#Cырые типы (raw type)]]
> - [ ] OK

> [!question]- Что такое вайлдкарды?
> ![[Generics#Wildcard]]
> - [ ] OK

> [!question]- Расскажите про принцип PECS
> ![[Generics#принцип PECS]]
> - [ ] OK

> [!question]- Можно ли выбрасывать исключение generic-типа?
> **Короткий ответ – да**.
> Как в большинстве каверзных вопросов про дженерики, ответ становится очевидным если подумать, во что сотрутся типы-параметры. Чтобы объявить, что метод выбрасывает исключение обобщенного типа T, этот тип T должен быть объявлен расширяющим Throwable. Именно в Throwable в таком случае сотрется T при компиляции. Также в качестве типа-верхней границы можно использовать любого наследника Throwable.
> - [ ] OK

> [!question]- Дженерики в исключениях – что можно, а что нельзя?
>1. **Можно выбрасывать исключение generic-типа.**
>	Тип-параметр T может использоваться в throws, переменная типа T может использоваться в throw.
>2. **Нельзя использовать дженерик в catch.**
>	Множественные блоки catch должны идти без повторений, в определенном порядке – от специфичного класса к более базовому. Стирание типов-параметров в связи с этими правилами добавило бы путаницу, не неся особой пользы.
>3. **Нельзя параметризовать класс-исключение типами.**
>	Если вы попытаетесь скомпилировать конструкцию вида `class MyException<T> extends Throwable {}`, то увидите ошибку `generic class may not extend java.lang.Throwable.`
>4. **Можно реализовывать исключением generic-интерфейс.**
>	Исключение вполне может быть, например Comparable или Iterable. Механизм обработки исключений работает на классах, никак не затрагивая интерфейсы.
> - [ ] OK

## Collections
Вопросов в разделе: `= (length(filter(this.file.tasks.section, (h) => meta(h).subpath = "Collections")))`

> [!question]- Что такое коллекции?
> ![[Collections#Collection]]
> - [ ] OK

> [!question]- Расскажите про иерархию коллекций
> ![[Collections#Иерархия коллекций]]
> - [ ] OK

> [!question]- Почему Map — это не Collection, в то время как List и Set являются Collection?
> ![[Collections#Почему Map — это не Collection]]
> - [ ] OK

> [!question]- В чем разница между классами java.util.Collection и java.util.Collections?
> ![[Collections#В чем разница между классами java.util.Collection и java.util.Collections?]]
> - [ ] OK

> [!question]- Какая разница между итераторами с fail-fast и fail-safe поведением?
> ![[Collections#Какая разница между итераторами с fail-fast и fail-safe поведением?]]
> - [ ] OK

> [!question]- Чем различаются Enumeration и Iterator?
> ![[Collections#Чем различаются Enumeration и Iterator?]]
> - [ ] OK

> [!question]- Как между собой связаны Iterable, Iterator и «for-each»?
> ![[Collections#Как между собой связаны Iterable, Iterator и «for-each»?]]
> - [ ] OK

> [!question]- Можно ли, обходя ArrayList, удалить элемент? Какое вылетит исключение?
> ![[Collections#Можно ли итерируясь по ArrayList удалить элемент? Какое вылетит исключение?]]
> - [ ] OK

> [!question]- Как поведёт себя коллекция, если вызвать iterator.remove()?
> ![[Collections#Как поведёт себя коллекция, если вызвать iterator.remove()?]]
> - [ ] OK

> [!question]- Чем Set отличается от List?
> ![[Collections#Чем Set отличается от List?]]
> - [ ] OK

> [!question]- Расскажите про интерфейс Set.
> ![[Collections#Расскажите про интерфейс Set.]]
> - [ ] OK

> [!question]- Расскажите про реализации интерфейса Set
> ![[Collections#Расскажите про реализации интерфейса Set]]
> - [ ] OK

> [!question]- Зачем нужны и чем отличаются интерфейсы Comparable и Comparator?
> ![[Collections#Зачем нужны и чем отличаются интерфейсы Comparable и Comparator?]]
> - [ ] OK

> [!question]- В чем отличия TreeSet и HashSet?
> ![[Collections#В чем отличия TreeSet и HashSet?]]
> - [ ] OK

> [!question]- Чем LinkedHashSet отличается от HashSet?
> ![[Collections#Чем LinkedHashSet отличается от HashSet?]]
> - [ ] OK

> [!question]- Что будет, если добавлять элементы в TreeSet по возрастанию?
> ![[Collections#Что будет, если добавлять элементы в TreeSet по возрастанию?]]
> - [ ] OK

> [!question]- Как устроен HashSet, сложность основных операций.
> ![[Collections#Как устроен HashSet, сложность основных операций.]]
> - [ ] OK

> [!question]- Как устроен LinkedHashSet, сложность основных операций
> ![[Collections#Как устроен LinkedHashSet, сложность основных операций.]]
> - [ ] OK

> [!question]- Как устроен TreeSet, сложность основных операций.
> ![[Collections#Как устроен TreeSet, сложность основных операций]]
> - [ ] OK

> [!question]- Расскажите про интерфейс List
> ![[Collections#Расскажите про интерфейс List]]
> - [ ] OK

> [!question]- Как устроен ArrayList, сложность основных операций.
> ![[Collections#Как устроен ArrayList, сложность основных операций.]]
> - [ ] OK

> [!question]- Как устроен LinkedList, сложность основных операций.
> ![[Collections#Как устроен LinkedList, сложность основных операций]]
> - [ ] OK

> [!question]- Как устроен LinkedList, сложность основных операций.
> ![[Collections#Как устроен LinkedList, сложность основных операций]]
> - [ ] OK

> [!question]- Почему LinkedList реализует и List, и Deque?
> ![[Collections#Почему LinkedList реализует и List, и Deque?]]
> - [ ] OK

> [!question]- Чем отличаются ArrayList и LinkedList?
> ![[Collections#Чем отличаются ArrayList и LinkedList?]]
> - [ ] OK

> [!question]- Что такое Queue?
> ![[Collections#Что такое Queue?]]
> - [ ] OK

> [!question]- Что такое Deque? Чем отличается от Queue?
> ![[Collections#Что такое Deque? Чем отличается от Queue?]]
> - [ ] OK

> [!question]- Приведите пример реализации Deque.
> ![[Collections#Приведите пример реализации Deque]]
> - [ ] OK

> [!question]- Какая коллекция реализует FIFO?
> ![[Collections#Какая коллекция реализует FIFO?]]
> - [ ] OK

> [!question]- Какая коллекция реализует LIFO?
> ![[Collections#Какая коллекция реализует LIFO?]]
> - [ ] OK

> [!question]- Оцените количество памяти на хранение одного примитива типа byte в LinkedList?
> ![[Collections#Оцените количество памяти на хранение одного примитива типа byte в LinkedList?]]
> - [ ] OK

> [!question]- Оцените количество памяти на хранение одного примитива типа byte в ArrayList?
> ![[Collections#Оцените количество памяти на хранение одного примитива типа byte в ArrayList?]]
> - [ ] OK

> [!question]- Какие существуют реализации Map?
> ![[Collections#Какие существуют реализации Map?]]
> - [ ] OK

> [!question]- Как устроена HashMap? (Расскажите про принцип корзин)
> ![[Collections#Как устроена HashMap? (Расскажите про принцип корзин)]]
> - [ ] OK

> [!question]- Что такое LinkedHashMap? LinkedHashMap - что в нем от LinkedList, а что от HashMap?
> ![[Collections#Что такое LinkedHashMap? LinkedHashMap - что в нем от LinkedList, а что от HashMap?]]
> - [ ] OK

> [!question]- Как устроена TreeMap, сложность основных операций?
> ![[Collections#Как устроена TreeMap, сложность основных операций?]]
> - [ ] OK

> [!question]- Что такое WeakHashMap?
> ![[Collections#Что такое WeakHashMap?]]
> - [ ] OK

> [!question]- Как работает HashMap при попытке сохранить в него два элемента по ключам с одинаковым hashCode(), но для которых equals() == false?
> ![[Collections#Как работает HashMap при попытке сохранить в него два элемента по ключам с одинаковым hashCode(), но для которых equals() == false?]]
> - [ ] OK

> [!question]- Что будет, если мы кладем в HashMap ключ, у которого equals и hashCode определены некорректно?
> ![[Collections#Что будет, если мы кладем в HashMap ключ, у которого equals и hashCode определены некорректно?]]
> - [ ] OK

> [!question]- Возможна ли ситуация, когда HashMap выродится в список даже с ключами имеющими разные hashCode()?
> ![[Collections#Возможна ли ситуация, когда HashMap выродится в список даже с ключами имеющими разные hashCode()?]]
> - [ ] OK

> [!question]- Почему нельзя использовать byte[] в качестве ключа в HashMap?
> ![[Collections#Почему нельзя использовать byte[] в качестве ключа в HashMap?]]
> - [ ] OK

> [!question]- Будет ли работать HashMap, если все добавляемые ключи будут иметь одинаковый hashCode()?
> ![[Collections#Будет ли работать HashMap, если все добавляемые ключи будут иметь одинаковый hashCode()?]]
> - [ ] OK

> [!question]- Какое худшее время работы метода get(key) для ключа, которого НЕТ в HashMap?
> ![[Collections#Какое худшее время работы метода get(key) для ключа, которого НЕТ в HashMap?]]
> - [ ] OK

## Функциональные интерфейсы
Вопросов в разделе: `= (length(filter(this.file.tasks.section, (h) => meta(h).subpath = "Функциональные интерфейсы")))`

> [!question]- Что такое функциональный интерфейс?
> ![[Функциональные интерфейсы#Что такое функциональный интерфейс?]]
> - [ ] OK

> [!question]- Для чего нужна аннотация @FunctionalInterface?
> ![[Функциональные интерфейсы#Для чего нужна аннотация @FunctionalInterface?]]
> - [ ] OK

> [!question]- Какие встроенные функциональные интерфейсы вы знаете?
> ![[Функциональные интерфейсы#Какие встроенные функциональные интерфейсы вы знаете?]]
> - [ ] OK

> [!question]- Все способы реализации функционального интерфейса?
> ![[Функциональные интерфейсы#Все способы реализации функционального интерфейса?]]
> - [ ] OK

> [!question]- Что такое ссылка на метод?
> ![[Функциональные интерфейсы#Что такое ссылка на метод?]]
> - [ ] OK

> [!question]- Что такое лямбда-выражение? Чем его можно заменить?
> ![[Функциональные интерфейсы#Что такое лямбда-выражение? Чем его можно заменить?]]
> - [ ] OK

> [!question]- Как можно и как нельзя? Иногда на собеседованиях просят найти ошибку в коде.
> ![[Функциональные интерфейсы#Как можно и как нельзя? Иногда на собеседованиях просят найти ошибку в коде]]
> - [ ] OK

## Stream API
Вопросов в разделе: `= (length(filter(this.file.tasks.section, (h) => meta(h).subpath = "Stream API")))`

> [!question]- Что такое Stream API? Для чего нужны стримы? http
> ![[Функциональные интерфейсы#Как можно и как нельзя? Иногда на собеседованиях просят найти ошибку в коде]]
> - [ ] OK

