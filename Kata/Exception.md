---
tags:
  - kata
  - java
  - core
  - oop
---
## Exception
Исключение в Java — это объект, который описывает исключительное состояние, возникшее в каком-либо участке программного кода (событие, ошибка). Когда возникает исключительное состояние, создается объект класса Exception. Этот объект пересылается в метод, обрабатывающий данный тип исключительной ситуации. Исключения могут возбуждаться и для того, чтобы сообщить о некоторых нештатных ситуациях.

## Hierarchy
1. класс **Throwable** (checked)
2. от Throwable  -> **Error** (ошибки JVM) и **Exception** (checked общие)
3. от Exception  -> **RuntimeException** (unchecked) -> **IOException, SQLException, ReflectiveOperationException** (checked)
4. RuntimeException (unchecked):   **ClassCastExceptiuon   IndexOutOfBoundException   AritthmeticException   NullPointerException**
![[Exceptions.png|600]]

## Checked / Unchecked
1. **Checked** исключения, это те, которые должны обрабатываться блоком catch или описываться в сигнатуре метода.
2. Unchecked могут не обрабатываться и не быть описанными.
> [!info] **Unchecked** исключения в Java — наследованные от `RuntimeException`, **checked** — от `Exception`.

- Наличие\\обработка Checked исключения проверяются компилятором на этапе компиляции.
- Наличие\\обработка Unchecked исключения происходит на этапе выполнения.

**СИНТАКСИС И ИДЕОЛОГИЯ**:
- Можно ловить и checked, и unchecked, но ловить unchecked не нужно. И обрабатывать, собственно, нужно только checked исключения.
- Unchecked исключения не Error, но RunTimeException это больше ошибка кода (программиста), которую нужно исправить.