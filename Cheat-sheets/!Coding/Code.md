# Задачи по программированию на Java

## Задача 1: Развернуть строку (3 способами)

**Вопрос:** Напишите программу на Java, которая разворачивает строку тремя различными способами.

**Решение:**

```java
public class ReverseString {
    public static void main(String[] args) {
        String original = "Hello, World!";
        
        // Способ 1: Использование StringBuilder
        StringBuilder sb = new StringBuilder(original);
        String reversed1 = sb.reverse().toString();
        System.out.println("Способ 1: " + reversed1);
        
        // Способ 2: Использование массива символов
        char[] chars = original.toCharArray();
        int left = 0, right = chars.length - 1;
        while (left < right) {
            char temp = chars[left];
            chars[left] = chars[right];
            chars[right] = temp;
            left++;
            right--;
        }
        String reversed2 = new String(chars);
        System.out.println("Способ 2: " + reversed2);
        
        // Способ 3: Рекурсия
        String reversed3 = reverseStringRecursive(original);
        System.out.println("Способ 3: " + reversed3);
    }
    
    private static String reverseStringRecursive(String str) {
        if (str.isEmpty()) {
            return str;
        }
        return reverseStringRecursive(str.substring(1)) + str.charAt(0);
    }
}
```

1. **Использование StringBuilder:**  
   Создайте объект `StringBuilder`, передайте в него строку и вызовите метод `reverse()`. Затем преобразуйте результат обратно в строку.

2. **Использование массива символов:**  
   Преобразуйте строку в массив символов. Используйте два указателя (один в начале, другой в конце массива) и меняйте символы местами, пока указатели не встретятся.

3. **Рекурсия:**  
   Напишите рекурсивную функцию, которая будет брать подстроку (без первого символа) и добавлять первый символ в конец результата.

---

## Задача 2: Проверка на палиндром

**Вопрос:** Напишите программу на Java, которая проверяет, является ли строка палиндромом.

**Решение:**

```java
public class PalindromeCheck {
    public static void main(String[] args) {
        String str = "madam";
        boolean isPalindrome = isPalindrome(str);
        System.out.println("Строка \"" + str + "\" является палиндромом? " + isPalindrome);
    }
    
    private static boolean isPalindrome(String str) {
        int left = 0, right = str.length() - 1;
        while (left < right) {
            if (str.charAt(left) != str.charAt(right)) {
                return false;
            }
            left++;
            right--;
        }
        return true;
    }
}
```

Используйте два указателя: один в начале строки, другой в конце. Сравнивайте символы на этих позициях, постепенно сдвигая указатели к центру. Если все символы совпадают, строка является палиндромом.

---

## Задача 3: Поиск наибольшего элемента в массиве

**Вопрос:** Напишите программу на Java, которая находит наибольший элемент в массиве целых чисел.

**Решение:**

```java
public class FindMaxElement {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};
        int max = findMax(numbers);
        System.out.println("Наибольший элемент в массиве: " + max);
    }
    
    private static int findMax(int[] arr) {
        int max = arr[0];
        for (int num : arr) {
            if (num > max) {
                max = num;
            }
        }
        return max;
    }
}
```

Инициализируйте переменную `max` первым элементом массива. Пройдитесь по всем элементам массива, сравнивая каждый элемент с `max`. Если текущий элемент больше `max`, обновите значение `max`.

---

## Задача 4: Подсчет количества слов в строке

**Вопрос:** Напишите программу на Java, которая подсчитывает количество слов в строке.

**Решение:**

```java
public class WordCount {
    public static void main(String[] args) {
        String str = "Java is a powerful programming language";
        int wordCount = countWords(str);
        System.out.println("Количество слов в строке: " + wordCount);
    }
    
    private static int countWords(String str) {
        if (str == null || str.isEmpty()) {
            return 0;
        }
        String[] words = str.split("\\s+");
        return words.length;
    }
}
```

Используйте метод `split()` для разделения строки на массив слов по пробелам. Количество элементов в массиве будет равно количеству слов. Убедитесь, что строка не пустая или не равна `null`.

---

## Задача 5: Генерация чисел Фибоначчи

**Вопрос:** Напишите программу на Java, которая генерирует первые N чисел Фибоначчи.

**Решение:**

```java
public class Fibonacci {
    public static void main(String[] args) {
        int n = 10;
        System.out.println("Первые " + n + " чисел Фибоначчи:");
        for (int i = 0; i < n; i++) {
            System.out.print(fibonacci(i) + " ");
        }
    }
    
    private static int fibonacci(int n) {
        if (n <= 1) {
            return n;
        }
        return fibonacci(n - 1) + fibonacci(n - 2);
    }
}
```

Используйте рекурсивную функцию для вычисления чисел Фибоначчи. Каждое число Фибоначчи равно сумме двух предыдущих чисел. Для базовых случаев (0 и 1) верните соответствующее значение.

---

Этот документ содержит пять распространенных задач по программированию на Java с описанием решений. Каждая задача демонстрирует различные аспекты языка, такие как работа со строками, массивами, рекурсией и базовыми алгоритмами.