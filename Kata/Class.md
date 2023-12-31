---
tags:
  - kata
  - java
  - core
  - oop
---
## Виды классов в Java
**Top level class** (обычный класс верхнего уровня):
- abstract class (абстрактный);
- final class (финализированный).
**Interfaces** (Интерфейс)
**Enum** (Перечисление)
**Nested class** (Вложенный класс):

> [!info] Класс верхнего уровня
> класс, который не является вложенным классом.

> [!info] Вложенный класс
> любой класс, объявление которого происходит в теле другого класса или интерфейса.

> [!info] Sealed (Запечатанные классы)
> это такие классы и интерфейсы, которые могут запрещать наследовать или реализовывать себя.
> Изолированный класс или интерфейс можно наследовать или реализовывать только тем классам и интерфейсам, которым это разрешили.
> Класс запечатывается применением модификатора sealed прямо в определении класса.(Начиная с Java 15).
> ``` java
> public sealed class PaymentMethod permits CreditCard, PayPal, Bitcoin {
> 	// Члены класса
> }
> ```

## Вложенные классы
Класс называется вложенным (Nested class), если он определен внутри другого класса. Вложенный класс должен создаваться только для того, чтобы обслуживать обрамляющий его класс. Если вложенный класс оказывается полезен в каком-либо ином контексте, он должен стать классом верхнего уровня.
Вложенные классы имеют доступ ко всем (в том числе приватным) полям и методам внешнего класса, но не наоборот. Из-за этого разрешения использование вложенных классов приводит к некоторому нарушению инкапсуляции.
> [!tip] Если вложенный класс имеет модификатор static, то теряется неявная связь с внешним классом и экземпляры вложенного класса будут жить своей собственной, независимой жизнью.

**Существуют 4 категории вложенных классов:**
- Static nested class (статический вложенный класс) - статические вложенные классы;
- Member inner class (простой внутренний класс) - нестатические вложенные классы;
- Local inner class (локальный класс) - классы внутри методов;
- Anonymous inner class (анонимный класс) - классы которые создаются на ходу.
![[classes.png|500]]

## Local Inner Class
вложенный класс, который может быть декларирован в любом блоке, в котором разрешается декларировать переменные.
Как и простые внутренние классы (Member inner class) локальные классы имеют имена и могут использоваться многократно. Как и анонимные классы, они имеют окружающий их экземпляр только тогда, когда применяются в нестатическом контексте.
Локальные классы имеют следующие особенности:
- Видны только в пределах блока, в котором объявлены;
- Не могут быть объявлены как private/public/protected или static;
- Не могут иметь внутри себя статических объявлений (полей, методов, классов);
- Имеют доступ к полям и методам обрамляющего класса;
- Могут обращаться к локальным переменным и параметрам метода, если они объявлены с модификатором final.

## Anonymous inner class
Это вложенный локальный класс без имени, который разрешено декларировать в любом месте обрамляющего класса, разрешающем размещение выражений.
Создание экземпляра анонимного класса происходит одновременно с его объявлением.
В зависимости от местоположения анонимный класс ведет себя как статический либо как нестатический вложенный класс – в нестатическом контексте появляется окружающий его экземпляр.
Анонимные классы имеют несколько ограничений:
- Их использование разрешено только в одном месте программы (месте его создания)
- Применение возможно только в том случае, если после порождения экземпляра нет необходимости на него ссылаться
- Реализует лишь методы своего интерфейса или суперкласса, т.е. не может объявлять каких-либо новых методов, так как для доступа к ним нет поименованного типа.

Анонимные классы обычно применяются для: 
- создания объекта функции (function object), например реализация интерфейса Comparator;
- создания объекта процесса (process object), такого как экземпляры классов Thread, Runnable и подобных
- в статическом методе генерации;
- инициализации открытого статического поля final, которое соответствует сложному перечислению типов, когда для каждого экземпляра в перечислении требуется отдельный подкласс.

## Доступ к полям внешнего класса
Статический вложенный класс имеет прямой доступ **только** к статическим полям обрамляющего класса.
Простой внутренний класс, может обратиться к любому полю внешнего класса напрямую.
В случае, если у вложенного класса уже существует поле с таким же литералом, то обращаться к такому полю следует через ссылку на его экземпляр. `Outer.this.field.`


## Abstract Class
**Абстрактным** называется класс, на основе которого не могут создаваться объекты.
Создать можно только экземпляр класса-наследника, не являющегося абстрактным.
Наследниками абстрактного класса могут также быть другие абстрактные классы.

Модификатор `abstract` необходим для создания абстрактных классов и методов. Если класс объявлен как `abstract`, то единственная цель для него быть расширенным. Любой класс, который расширяет абстрактный класс должен реализовать все абстрактные методы суперкласса, если подкласс не является абстрактным классом.

Методы **abstract** никогда не могут быть final или static.
Если класс в Java содержит один или несколько абстрактных методов, то класс должен быть объявлен как abstract.

Абстрактные классы решают две задачи:
- определяют набор публичных методов (внешний контракт класса)
- содержат не публичные поля и методы (детали реализации)

Абстрактный класс не обязан содержать абстрактные методы.