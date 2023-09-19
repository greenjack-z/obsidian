---
tags:
  - kata
  - java
  - core
  - oop
---
## Ассоциация
означает, что объекты двух классов могут ссылаться один на другой, иметь связь друг с другом. Один класс включает в себя другой класс в качестве одного из полей.
> [!example] пример
> Оператор управляет Роботом. Соответственно возникает ассоциация между Роботом и Оператором. Ассоциация и есть описание связи между двумя объектами. Идея достаточно простая — два объекта могут быть связаны между собой и это надо как-то описать.

Реализация: В одном классе делается ссылка на другой и наоборот (не всегда). Дальше идет развитие данной идеи в зависимости от количества связей. Соединим Робота с Оператором, который им управляет. Между ними можно установить ассоциацию через ссылки в одном классе на другой класс. Класс Robot имеет ссылку на класс Operator и наоборот.

[[Association#Агрегация|Агрегация]] и [[Association#Композиция|композиция]] являются частными случаями ассоциации. Это более конкретизированные отношения между объектами.
## Агрегация
отношение, когда один объект является частью другого. Двигатель поставили в одну машину, потом в другую.
> [!info] Вложенный статический класс - агрегация
## Композиция
это более жёсткое отношение, когда объект не только является частью другого объекта, но и вообще не может принадлежат кому-то. Страница принадлежит только одной Книге.
> [!info] Вложенный класс - композиция