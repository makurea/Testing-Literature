# Задачи по программированию на Java☕

## Содержание:
- **Строки**
  - [Задача 1: Развернуть строку (StringBuilder и метод reverse())](#task1)  
  - [Задача 2: Развернуть строку (массив char)](#task2)
  - [Задача 2.1: Развернуть строку (массив char)](#task2.1)  
  - [Задача 3: Развернуть строку (цикл с StringBuilder)](#task3)  
  - [Задача 4: Развернуть строку (стек (Deque))](#task4)  
  - [Задача 5: 🔥Развернуть строку (использование рекурсии)](#task5)  
  - [Задача 6: Проверка на полиндром](#task6)  
  - [Задача 7: 🔥Подсчет вхождений символа в строке](#task7)
  - [Задача 8: Подсчет вхождений символа в строке - простой](#task8)
  - [Задача 9: 🔥Удаления дубликатов символов из строки](#task9)  
  - [Задача 10: Удаления дубликатов символов из строки - простой](#task10)
  - [Задача 11: Замена символов в строке](#task11)
    
- **Коллекции**
  - [Задача 1: Обмен ключей и значений в HashMap](#task1k)  

<a name="task1"></a>
## Задача 1: Развернуть строку (StringBuilder и метод reverse())

**Вопрос:** Напишите программу на Java, которая разворачивает строку.

**Решение:**

```java
public class ReverseUsingStringBuilder {
    public static void main(String[] args) {
        String input = "Привет, мир!";
        
        // Вызываем метод reverse и выводим результат
        String reversedString = reverse(input);
        System.out.println("Исходная строка: " + input);
        System.out.println("Обратная строка (StringBuilder): " + reversedString);
    }

    // Метод для反转 строки с использованием StringBuilder
    public static String reverse(String input) {
        StringBuilder reversed = new StringBuilder(input);
        return reversed.reverse().toString(); // Используем метод reverse()
    }
}
```

Использует StringBuilder и его метод reverse() для быстрого переворота строки.


---

<a name="task2"></a>
## Задача 2: Развернуть строку (массив char)

**Вопрос:** Напишите программу на Java, которая разворачивает строку.

**Решение:**

```java
public class ReverseUsingCharArray {

    // Метод reverse для переворота строки через массив char
    public static String reverse(String input) {
        if (input == null || input.isEmpty()) {
            return input; // Возвращаем исходную строку, если она пустая или null
        }

        char[] chars = input.toCharArray();
        for (int i = 0; i < chars.length / 2; i++) {
            // Меняем символы местами
            char temp = chars[i];
            chars[i] = chars[chars.length - i - 1];
            chars[chars.length - i - 1] = temp;
        }
        return new String(chars); // Преобразуем массив обратно в строку
    }

    public static void main(String[] args) {
        // Пример использования метода reverse
        String input = "Привет, мир!";
        String reversedString = reverse(input);
        System.out.println("Обратная строка (массив char): " + reversedString);
    }
}
```

работает напрямую с массивом символов (char[]) и меняет их местами.

---

<a name="task2.1"></a>
## Задача 2.1: Развернуть строку (массив char)

**Вопрос:** Напишите программу на Java, которая разворачивает строку.

**Решение:**

```java
    public class Main {
    public static void main(String[] args) {
        String s = "Hello, world!"; // Исходная строка
        System.out.println(reverseString(s)); // Вывод перевернутой строки
    }

    public static String reverseString(String s) {
        int length = s.length(); // Длина строки
        char[] chars = new char[length]; // Массив для хранения символов в обратном порядке
        int startCount = 0; // Индекс для заполнения массива

        for (int i = length - 1; i >= 0; i--) { // Перебираем символы строки с конца
            char tempChar = s.charAt(i); // Получаем текущий символ
            chars[startCount++] = tempChar; // Добавляем символ в массив
        }

        return new String(chars); // Возвращаем перевернутую строку
    }
}
```

**Массив** `chars`: Используется для хранения символов строки в обратном порядке.
**Цикл** `for`: Перебирает символы исходной строки с конца и добавляет их в массив `chars`.
**Метод** `reverseString`: Возвращает новую строку, созданную из массива символов.

---

<a name="task2"></a>
## Задача 3: Развернуть строку (цикл с StringBuilder)

**Вопрос:** Напишите программу на Java, которая разворачивает строку.

**Решение:**

```java
public class ReverseUsingStringBuilderLoop {

    public static void main(String[] args) {
        // Пример строки для переворота
        String input = "Привет, мир!";
        
        // Вызываем метод reverse и выводим результат
        String reversedString = reverse(input);
        System.out.println("Обратная строка (StringBuilder с циклом): " + reversedString);
    }

    // Метод reverse через StringBuilder
    public static String reverse(String input) {
        if (input == null || input.isEmpty()) {
            return input; // Возвращаем исходную строку, если она пустая или null
        }

        StringBuilder reversed = new StringBuilder();
        for (int i = input.length() - 1; i >= 0; i--) {
            reversed.append(input.charAt(i));
        }
        return reversed.toString();
    }
}
```

Использует цикл для добавления символов в StringBuilder в обратном порядке.


---

<a name="task4"></a>
## Задача 4: Развернуть строку (стек (Deque))

**Вопрос:** Напишите программу на Java, которая разворачивает строку.

**Решение:**

```java
public class ReverseUsingStack {

    public static void main(String[] args) {
        // Пример строки для переворота
        String input = "Привет, мир!";
        
        // Вызываем метод reverse и выводим результат
        String reversedString = reverse(input);
        System.out.println("Обратная строка (стек): " + reversedString);
    }

    // Метод reverse через стек
    public static String reverse(String input) {
        if (input == null || input.isEmpty()) {
            return input; // Возвращаем исходную строку, если она пустая или null
        }

        Deque<Character> stack = new ArrayDeque<>();
        for (int i = 0; i < input.length(); i++) {
            stack.push(input.charAt(i)); // Добавляем каждый символ в стек
        }

        StringBuilder sb = new StringBuilder();
        while (!stack.isEmpty()) {
            sb.append(stack.pop()); // Извлекаем символы из стека в обратном порядке
        }

        return sb.toString();
    }
}
```

Применяет стек (Deque) для хранения символов и их последующего извлечения в обратном порядке.


---

<a name="task5"></a>
## Задача 5: Развернуть строку (использование рекурсии)

**Вопрос:** Напишите программу на Java, которая разворачивает строку.

**Решение:**

```java
public class ReverseUsingRecursion {

    public static void main(String[] args) {
        // Пример строки для переворота
        String input = "Привет, мир!";
        
        // Вызываем метод reverse и выводим результат
        String reversedString = reverse(input);
        System.out.println("Обратная строка (рекурсия): " + reversedString);
    }

    // Метод reverse через рекурсию
    public static String reverse(String input) {
        if (input == null || input.isEmpty()) {
            return input; // Возвращаем пустую строку, если входная строка null или пустая
        }
        if (input.length() <= 1) {
            return input; // Базовый случай: если строка состоит из одного символа, возвращаем её
        }
        // Рекурсивный вызов: берем подстроку без первого символа и добавляем первый символ в конец
        return reverse(input.substring(1)) + input.charAt(0);
    }
}
```

Использует рекурсивный подход, где строка уменьшается на первый символ на каждом шаге, пока не станет пустой.


---

<a name="task6"></a>
## Задача 6: Проверка на полиндром

**Вопрос:** Напишите программу на Java, которая проверяет строку на полиндром.

**Решение:**

```java
public class PalindromeChecker {

    public static void main(String[] args) {
        // Исходная строка
        String input = "аргентина манит негра";
        
        // Проверяем, является ли строка палиндромом
        if (isPalindrome(input)) {
            System.out.println("Строка \"" + input + "\" является палиндромом.");
        } else {
            System.out.println("Строка \"" + input + "\" не является палиндромом.");
        }
    }

    // Метод для проверки строки на палиндром
    public static boolean isPalindrome(String input) {
        // Удаляем пробелы и приводим строку к нижнему регистру
        String cleanedInput = input.replaceAll("\\s", "").toLowerCase();
        
        // Сравниваем строку с её обратной версией
        String reversed = new StringBuilder(cleanedInput).reverse().toString();
        return cleanedInput.equals(reversed);
    }
}
```

---

<a name="task7"></a>
## Задача 7: Подсчет вхождений символа в строке

**Вопрос:** Напишите программу на Java, которая ищет кол-во вхождений символа в строку.

**Решение:**

```java
public class Main {
   public static void main(String[] args) {
      String input = "Potatoes";
      char seek = 'o';
      int count = (int) input.chars().filter(ch -> ch == seek).count();
      System.out.println(count);
  }
}
```
`input.chars()` - преобразует строку в поток (`IntStream`) целых чисел, где каждый символ представлен своим кодом ASCII/Unicode.  
`.filter(ch -> ch == c)` - фильтруем только те символы, которые равны нашему искомому символу `seek`.  
`.count()` - считаем количество оставшихся после фильтрации символов.  
`(int)` - приводим результат к типу `int`, так как `count()` возвращает `long`.  

---

<a name="task8"></a>
## Задача 8: Подсчет вхождений символа в строке

**Вопрос:** Напишите программу на Java, которая ищет кол-во вхождений символа в строку.

**Решение:**

```java
public class Main {
    public static void main(String[] args) {
        String input = "Potatoes"; // Исходная строка
        char seek = 'o'; // Искомый символ
        int count = 0; // Счетчик вхождений

        // Перебираем каждый символ в строке
        for (int i = 0; i < input.length(); i++) {
            if (input.charAt(i) == seek) { // Проверяем, совпадает ли символ с искомым
                count++; // Увеличиваем счетчик, если совпадение найдено
            }
        }

        System.out.println(count); // Выводим результат
    }
}
```
`input.length()` - возвращает длину строки.
`input.charAt(i)` - получает символ строки по индексу `i`.
Цикл `for` перебирает каждый символ строки.
Условие `if (input.charAt(i) == seek)` проверяет, совпадает ли текущий символ с искомым.
Если совпадение найдено, счетчик `count` увеличивается на 1.
После завершения цикла выводится количество вхождений.

---

<a name="task9"></a>
## Задача 9: Удаления дубликатов символов из строки

**Вопрос:** Напишите программу на Java, которая ищет дубликаты и удаляет их.

**Решение:**

```java
public class Main {
    public static void main(String[] args) {
        String s = "приветмирмир";
        String result = s.chars().distinct().collect(StringBuilder::new, StringBuilder::appendCodePoint, StringBuilder::append).toString();
        System.out.println(result);
    }
}
```
`s.chars()` - преобразует строку в поток (`IntStream`) целых чисел (коды символов).  
`.distinct()` - оставляет только уникальные символы, удаляя дубликаты.  
`.collect(...)` - собирает результат обратно в строку:  
 `StringBuilder::new` - создает новый `StringBuilder`.  
 `StringBuilder::appendCodePoint` - добавляет каждый уникальный символ.  
 `StringBuilder::append` - объединяет результаты.  
`.toString()` - преобразует `StringBuilder` обратно в строку.  

---

<a name="task10"></a>
## Задача 10: Удаления дубликатов символов из строки - простой 

**Вопрос:** Напишите программу на Java, которая ищет дубликаты и удаляет их.

**Решение:**

```java
public class Main {
    public static void main(String[] args) {
        String input = "приветмир"; // Исходная строка
        String result = removeDuplicates(input);
        System.out.println("Строка без дубликатов: " + result);
    }

    public static String removeDuplicates(String input) {
        if (input == null || input.isEmpty()) {
            return input; // Если строка пустая или null, возвращаем её как есть
        }

        StringBuilder sb = new StringBuilder(); // Для формирования результирующей строки
        HashSet<Character> seen = new HashSet<>(); // Множество для хранения уже встреченных символов

        for (char c : input.toCharArray()) { // Перебираем каждый символ строки
            if (!seen.contains(c)) { // Если символ ещё не встречался
                sb.append(c); // Добавляем его в результат
                seen.add(c); // Помечаем как встретившийся
            }
        }

        return sb.toString(); // Возвращаем строку без дубликатов
    }
}
```
`HashSet` - Мы используем `HashSet` для отслеживания символов, которые уже были обработаны. `HashSet` автоматически игнорирует повторяющиеся элементы.     
`StringBuilder` : Используется для эффективного построения новой строки без дубликатов.  
`Цикл` : Каждый символ строки проверяется на наличие в множестве `seen`. Если символ ещё не был добавлен, он добавляется в результат.  

---

<a name="task11"></a>
## Задача 11: Замена символов в строке 

**Вопрос:** Напишите программу на Java, которая заменяет все вхождения определённого символа на другой символ в строке.

**Решение:**

```java
public class Task1 {
    public static void main(String[] args) {
        // Неуд*ч* - это просто возможность начать снов*, но уже более мудро
        // Заменить все звездочки на букву a
        String s = "Неуд*ч* - это просто возможность начать снов*, но уже более мудро"; // Исходная строка
        System.out.println(replaceSymbols(s, '*', 'a')); // Вывод строки с заменёнными символами
    }

    public static String replaceSymbols(String s, char oldChar, char newChar) {
        char[] chars = s.toCharArray(); // Преобразуем строку в массив символов

        for (int i = 0; i < chars.length; i++) { // Перебираем каждый символ массива
            if (chars[i] == oldChar) { // Если текущий символ совпадает с oldChar
                chars[i] = newChar; // Заменяем его на newChar
            }
        }

        return String.valueOf(chars); // Возвращаем строку, созданную из массива символов
    }
}
```
**Массив `chars`:** Используется для хранения символов строки, чтобы можно было изменять их.  
**Цикл `for`:** Перебирает каждый символ массива и заменяет его, если он совпадает с `oldChar`.  
**Метод `replaceSymbols`:** Возвращает новую строку с заменёнными символами.  


---

<a name="task1k"></a>
## Задача 1: Обмен ключей и значений в HashMap

**Вопрос:** Напишите программу на Java, которая меняет местами ключи и значения в HashMap. На вход в метод поступает HashMap<Integer, String>, а на выходе должен быть HashMap<String, Integer>.

**Решение:**

```java
public class Main {
    public static void main(String[] args) {
        // Создаём исходный HashMap
        HashMap<Integer, String> map = new HashMap<>();
        map.put(1, "один");
        map.put(2, "два");
        map.put(3, "три");

        // Выводим исходный HashMap
        System.out.println("Исходный HashMap: " + map);

        // Выводим HashMap с поменянными ключами и значениями
        System.out.println("HashMap после обмена: " + returnMap(map));
    }

    public static HashMap<String, Integer> returnMap(HashMap<Integer, String> map) {
        // Создаём новый HashMap для хранения результата
        HashMap<String, Integer> map2 = new HashMap<>();

        // Перебираем все пары ключ-значение из исходного HashMap
        for (Map.Entry<Integer, String> entry : map.entrySet()) {
            // Меняем местами ключ и значение и добавляем в новый HashMap
            map2.put(entry.getValue(), entry.getKey());
        }

        return map2; // Возвращаем новый HashMap
    }
}
```
**Исходный `HashMap`**: Содержит пары Integer (ключ) и `String` (значение).  
**Метод `returnMap`**: Принимает `HashMap<Integer, String>`, создаёт новый `HashMap<String, Integer>` и заполняет его, меняя местами ключи и значения.  
**Цикл `for`**: Перебирает все пары ключ-значение из исходного `HashMap` с помощью `entrySet()`.  
**Результат**: Возвращается новый `HashMap`, где ключи и значения поменялись местами.  






