# Задачи по программированию на Java☕

## Содержание:
[Задача 1: Развернуть строку (StringBuilder и метод reverse())](#task1)  
[Задача 2: Развернуть строку (массив char)](#task2)  
[Задача 3: Развернуть строку (цикл с StringBuilder)](#task3)  
[Задача 4: Развернуть строку (стек (Deque))](#task4)  
[Задача 5: Развернуть строку (использование рекурсии)](#task5)  
[Задача 6: Проверка на полиндром](#task6)  
[Задача 7: Подсчет вхождений символа в строке](#task7)

[Задача 9: Удаления дубликатов символов из строки](#task9)


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

<a name="task1"></a>
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

аботает напрямую с массивом символов (char[]) и меняет их местами.

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






