---
tags:
  - kata
  - java
  - core
  - oop
---

Java разрешает определение внутри одного класса двух или более методов с одним именем, если только объявления их параметров различны. В этом случае методы называют перегруженными, а процесс — перегрузкой методов. За счёт этого можно, например, эмулировать значение по умолчанию для параметров.
> [!info] Справка: [[Constructor|Конструкторы]] (так же, как и методы) могут быть перегружены. Бывают дефолтный (не принимающий аргументы) и параметризированный. Это определяется во время создания объекта. Есть также конструктор копирования см. дальше).