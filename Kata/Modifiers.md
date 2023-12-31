---
tags:
  - kata
  - java
  - core
  - oop
---

Модификаторы — ключевые слова, которые добавляют при инициализации для изменения значений. Чтобы использовать модификатор в Java, нужно включить его ключевое слово в определение класса, метода или переменной.
Существует два вида модификаторов в java:
- Access modifier: модификаторы доступа (private, default (по умолчанию), protected, public).
- Non-access modifiers: модификаторы класса, метода, переменной и потока, используемые НЕ для доступа (final, static, abstract, synchronized, native, volatile, transient …).

## Модификаторы доступа
Модификаторы доступа позволяют задать допустимую области видимости для членов класса, то есть контекст, в котором можно употреблять данную переменную или метод.
### private
доступ к компоненту только из класса, в котором объявлен
### default (package private)
Переменная или метод будут доступны для любого другого класса в том же пакете.
### protected
Поля protected доступны всем классам внутри пакета, а также всем классам-наследникам вне пакета.
### public
доступ к компоненту из экземпляра любого класса и любого пакета.

> [!tip] Класс верхнего уровня может быть объявлен с модификатором public или default. Вложенный класс - с любым модификатором.


## final
- final Class - от класса нельзя наследоваться
- final field - значение полю можно присвоить только один раз. После чего изменять его будет нельзя. Для ссылочных переменных это означает, что после присвоения объекта, нельзя изменить ссылку на данный объект. Важно: Ссылку изменить нельзя, но состояние объекта изменять можно.
- final method - метод нельзя переопределить в классах-наследниках

## static
- static **Class** - это вложенный класс, который может обращаться только к статическим полям обертывающего его класса.

- static **field** - переменная, принадлежащая классу, а не объекту. К ней можно обратиться не создавая экземпляр класса.
> [!warning] В Java локальные переменные не могут быть static.

> [!tip] static final - используется для объявления констант

- static **method** - метод можно вызывать, не создавая экземпляр содержащего его класса. Внутри static метода нельзя вызвать не статический метод по имени класса.

## abstract
- abstract Class - абстрактный класс
- abstract method - абстрактный метод (в абстрактном классе)