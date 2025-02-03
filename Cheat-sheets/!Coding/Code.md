# Задачи по программированию на Java☕

## Содержание:
[Задача 1: Развернуть строку (3 способами)](#task1)  
[Задача 2: Проверка на палиндром)](#task2)  
[Задача 3: Поиск наибольшего элемента в массиве](#task3)  
[Задача 4: Подсчет количества слов в строке](#task4)  
[Задача 5: Генерация чисел Фибоначчи](#task5)  
[Задача 6: Проверка на анaграмму](#task6)  
[Задача 7: Сортировка массива методом пузырька](#task7)    
[Задача 8: Удаление дубликатов символов в строке](#remove-duplicates-string)  
[Задача 9: Проверка, содержит ли массив заданное число](#array-contains-number)  
[Задача 10: Удаление дубликатов из массива](#remove-duplicates-array)  
[Задача 11: Объединение двух отсортированных массивов](#merge-sorted-arrays)  
[Задача 12: Проверка, является ли число простым](#prime-number-check)  
[Задача 13: Вычисление факториала числа](#factorial-calculation)  

<a name="task1"></a>
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
<a name="task2"></a>
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
<a name="task3"></a>
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
<a name="task4"></a>
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
<a name="task5"></a>
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
<a name="task6"></a>
## Задача 6: Проверка на анaграмму

**Вопрос:** Напишите программу на Java, которая проверяет, являются ли две строки анaграммами.

**Решение:**

```java
public class AnagramCheck {
    public static void main(String[] args) {
        String str1 = "listen";
        String str2 = "silent";
        boolean isAnagram = areAnagrams(str1, str2);
        System.out.println("Строки \"" + str1 + "\" и \"" + str2 + "\" являются анagramмами? " + isAnagram);
    }
    
    private static boolean areAnagrams(String str1, String str2) {
        if (str1.length() != str2.length()) {
            return false;
        }
        int[] charCount = new int[256];
        for (int i = 0; i < str1.length(); i++) {
            charCount[str1.charAt(i)]++;
            charCount[str2.charAt(i)]--;
        }
        for (int count : charCount) {
            if (count != 0) {
                return false;
            }
        }
        return true;
    }
}
```

Использование массива для подсчета количества каждого символа в обеих строках и сравнение результатов.

---
<a name="task7"></a>
## Задача 7: Сортировка массива методом пузырька

**Вопрос:** Напишите программу на Java, которая сортирует массив целых чисел методом пузырька.

**Решение:**

```java
public class BubbleSort {
    public static void main(String[] args) {
        int[] numbers = {64, 34, 25, 12, 22, 11, 90};
        bubbleSort(numbers);
        System.out.println("Отсортированный массив:");
        for (int num : numbers) {
            System.out.print(num + " ");
        }
    }
    
    private static void bubbleSort(int[] arr) {
        int n = arr.length;
        boolean swapped;
        for (int i = 0; i < n - 1; i++) {
            swapped = false;
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    // Обмен элементов
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swapped = true;
                }
            }
            // Если не было обменов, массив отсортирован
            if (!swapped) {
                break;
            }
        }
    }
}
```

Реализация сортировки пузырьком, где элементы сравниваются и меняются местами, если они находятся в неправильном порядке.

---

## <a name="task8"></a> 8. Удаление дубликатов символов в строке

```java
public class RemoveDuplicatesFromString {
    public static void main(String[] args) {
        String input = "programming";
        String result = removeDuplicates(input);
        System.out.println("Строка без дубликатов: " + result);
    }

    private static String removeDuplicates(String str) {
        StringBuilder sb = new StringBuilder();
        boolean[] seen = new boolean[256];
        for (char c : str.toCharArray()) {
            if (!seen[c]) {
                sb.append(c);
                seen[c] = true;
            }
        }
        return sb.toString();
    }
}
```

---

## <a name="task9"></a> 9. Проверка, содержит ли массив заданное число

```java
public class ArrayContainsNumber {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};
        int target = 3;
        boolean contains = containsNumber(numbers, target);
        System.out.println("Массив содержит " + target + "? " + contains);
    }

    private static boolean containsNumber(int[] arr, int num) {
        for (int n : arr) {
            if (n == num) {
                return true;
            }
        }
        return false;
    }
}
```

---

## <a name="task10"></a> 10. Удаление дубликатов из массива

```java
public class RemoveDuplicatesFromArray {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 2, 3, 4, 4, 5};
        int[] uniqueNumbers = removeDuplicates(numbers);
        System.out.println("Массив без дубликатов: ");
        for (int num : uniqueNumbers) {
            System.out.print(num + " ");
        }
    }

    private static int[] removeDuplicates(int[] arr) {
        return java.util.Arrays.stream(arr).distinct().toArray();
    }
}
```

---

## <a name="task11"></a> 11. Объединение двух отсортированных массивов

```java
public class MergeSortedArrays {
    public static void main(String[] args) {
        int[] arr1 = {1, 3, 5, 7};
        int[] arr2 = {2, 4, 6, 8};
        int[] mergedArray = mergeSortedArrays(arr1, arr2);
        System.out.println("Объединенный массив:");
        for (int num : mergedArray) {
            System.out.print(num + " ");
        }
    }

    private static int[] mergeSortedArrays(int[] arr1, int[] arr2) {
        int[] result = new int[arr1.length + arr2.length];
        int i = 0, j = 0, k = 0;
        while (i < arr1.length && j < arr2.length) {
            if (arr1[i] < arr2[j]) {
                result[k++] = arr1[i++];
            } else {
                result[k++] = arr2[j++];
            }
        }
        while (i < arr1.length) {
            result[k++] = arr1[i++];
        }
        while (j < arr2.length) {
            result[k++] = arr2[j++];
        }
        return result;
    }
}
```

---

## <a name="task12"></a> 12. Проверка, является ли число простым

```java
public class PrimeNumberCheck {
    public static void main(String[] args) {
        int num = 29;
        boolean isPrime = isPrime(num);
        System.out.println("Число " + num + " является простым? " + isPrime);
    }

    private static boolean isPrime(int num) {
        if (num < 2) {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                return false;
            }
        }
        return true;
    }
}
```

---

## <a name="task13"></a> 13. Вычисление факториала числа

```java
public class FactorialCalculation {
    public static void main(String[] args) {
        int num = 5;
        long factorial = factorial(num);
        System.out.println("Факториал числа " + num + " равен " + factorial);
    }

    private static long factorial(int n) {
        if (n == 0) {
            return 1;
        }
        return n * factorial(n - 1);
    }
}
```

---


