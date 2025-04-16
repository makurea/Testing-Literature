# 🧭 XPath Cheatsheet – Быстрый справочник по XPath

## 📌 Общая информация

- XPath — язык для навигации по элементам XML/HTML-документа.
- XPath можно тестировать в **Xpath test bed (whitebeam.org)** или в **консоли браузера**:
  ```javascript
  $x("//div") // Работает в Chrome и Firefox
  ```

---

## 📁 Селекторы и базовые выражения

### 🔹 Простые селекторы
```xpath
//h1                  # Все h1
//div//p              # Все p внутри div (на любой глубине)
//ul/li               # li — прямые потомки ul
/div/*               # Все прямые дочерние элементы div
/                    # Корневой элемент (обычно html)
/body                # Корневой body
```

### 🔹 Атрибуты
```xpath
//*[@id="id"]                             # Элемент с id="id"
//*[@class="class"]                       # Точный класс (редко работает корректно)
//input[@type="submit"]                   # input с type="submit"
//a[@id="abc"][@for="xyz"]                # Несколько атрибутов
//a[@rel]                                 # Элемент, у которого есть rel
//a[starts-with(@href, '/')]              # href начинается с '/'
//a[ends-with(@href, '.pdf')]             # href заканчивается на '.pdf'
//a[contains(@href, '://')]               # href содержит '://'
//a[contains(@rel, 'help')]               # rel содержит help (осторожно)
```

### 🔹 Класс через `contains + normalize-space`
```xpath
//div[contains(concat(' ', normalize-space(@class), ' '), ' my-class ')]
```

---

## 🔢 Индексация и позиционирование

### 🔹 Простая индексация
```xpath
//li[1]                    # Первый элемент
//li[last()]               # Последний элемент
//li[position()=2]         # Второй элемент
//li[position()>1]         # Все, начиная со второго
//li[position() mod 2 = 1] # Нечётные элементы
```

### 🔹 Совмещение условий
```xpath
//ul/li[position() <= 3 and @class="item"]
//div[position() = last() - 1]    # Предпоследний
```

---

## 🧠 Логические выражения

### 🔹 Условия
```xpath
//a[@name or @href]
//div[@id="head" and position()=2]
//div[(x and y) or not(z)]
```

---

## 🔍 Поиск по тексту

### 🔹 Точное совпадение
```xpath
//button[text()="Submit"]
//*[normalize-space(text())="Submit"]
```

### 🔹 Частичное совпадение
```xpath
//button[contains(text(),"Go")]
```

### 🔹 Разница между `.` и `text()`
```xpath
//div[.="Hello"]                 # Весь текст узла
//span/text()                    # Текстовый узел (Node)
```

---

## 🌲 Оси (axes)

### 🔹 Популярные оси
```xpath
//div/child::span                 # Прямой потомок span
//div/descendant::span           # Все вложенные span
//div/ancestor::section          # Предки типа section
//div/ancestor-or-self::section  # Предок section или сам div
//div/parent::body               # Родитель body
//div/following-sibling::p       # Братья справа
//div/preceding-sibling::p       # Братья слева
//div/following::span            # Все span дальше по DOM
//div/preceding::span            # Все span перед div
//self::div                      # Сам элемент
//attribute::id                  # Атрибут id
```

> `//` = `descendant-or-self::node()/`
> `.` = `self::node()`
> `..` = `parent::node()`

---

## 🧬 Предикаты (фильтры)

### 🔹 Основы
```xpath
//div[true()]
//div[@class="head"]
//div[@class="head"][@id="top"]
```

### 🔹 Комбинация условий
```xpath
//ul[li]                         # ul, содержащие хотя бы один li
//ul[li[@class='hidden']]        # ul с li с классом hidden
//ul[count(li) > 2]              # ul, содержащие >2 li
```

---

## 🛠 XPath функции

### 🔹 Работа с узлами
```xpath
count(//*)                          # Кол-во всех элементов
//ul[count(li) > 2]                 # ul с более чем двумя li
//section[.//h1[@id='hi']]          # section с h1 с id=hi
```

### 🔹 Функции по типу
```xpath
text()                     # Текст узла
name()                     # Имя тега
position()                 # Позиция узла
last()                     # Последний узел
```

### 🔹 Логические функции
```xpath
not(expr)                  # Отрицание условия
```

### 🔹 Строковые функции
```xpath
contains(str, substr)
starts-with(str, prefix)
ends-with(str, suffix)
normalize-space()
concat(a, b)
substring(str, start, len)
substring-before(str, delim)
substring-after(str, delim)
```

---

## 🔗 Объединение и вложенность

### 🔹 Объединение результатов
```xpath
//a | //span           # Все <a> и <span>
```

### 🔹 Вложенные предикаты
```xpath
//section[.//h1[@id='section-name']]
```

---

## 🧪 Сравнение с jQuery

| jQuery                         | XPath |
|-------------------------------|-------|
| $('ul > li').parent()         | `//ul/li/..` |
| $('li').closest('section')    | `//li/ancestor-or-self::section` |
| $('a').attr('href')           | `//a/@href` |
| $('span').text()              | `//span/text()` |
| $('div.class')                | `//div[contains(concat(' ', normalize-space(@class), ' '), ' class ')]` |

---

## 📊 Примеры

```xpath
//*                                # Все элементы
(//h1)[1]/text()                  # Текст первого h1
//li[span]                        # li, внутри которого есть span
//ul/li/..                        # Родитель ul у li
//section[h1[@id='section-name']] # section, содержащий h1#section-name
```

```
