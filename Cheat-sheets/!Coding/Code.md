# Задачи по программированию на Java☕ <a name="contents"></a>           

## Содержание: <a id="Содержание"></a> 
- **Строки**
  - [🔄 Развернуть строку (массив char)](#reverse-string-char-array)
  - [🔄 Развернуть строку (цикл с StringBuilder)](#reverse-string-stringbuilder)  
  - [🔄 Развернуть строку (стек Deque)](#reverse-string-deque)  
  - [🔥 Развернуть строку (использование рекурсии)](#reverse-string-recursion)
  - [🌀 Развернуть строку (рекурсия и лямбда-выражение)](#reverse-string-recursion-lambda)
  - [🔥 Развернуть строку (чистая рекурсия)](#reverse-string-pure-recursion)  
  - [✅ Проверка на палиндром](#check-palindrome)  
  - [🔥 Подсчет вхождений символа в строке (Map)](#count-char-occurrences-map)
  - [📊 Подсчет вхождений символа в строке (простой)](#count-char-occurrences-simple)
  - [🔥 Удаление дубликатов символов из строки (Set)](#remove-duplicates-set)  
  - [🧹 Удаление дубликатов символов из строки (простой)](#remove-duplicates-simple)
  - [🔄 Замена символов в строке](#replace-characters)
  - [📌 Разделение строки на числа и буквы, подсчет суммы чисел](#split-string-sum-numbers)
  - [📚 Перестановки строки (рекурсия)](#string-permutations-recursion)
  - [🧩 Наибольшая общая подстрока двух строк](#longest-common-substring)
  - [🔍 Проверка на уникальность символов в строке (Set)](#is-unique-characters)
  - [🆚 Являются ли строки анаграммами](#check-anagram)  ---
  - [🔢 Подсчет количества слов в строке](#count-words-in-string)
  - [🧵 Удаление всех пробелов из строки](#remove-all-whitespaces)
  - [📐 Является ли строка перестановкой другой](#is-permutation)
  - [🔄 Инвертировать порядок слов в строке](#reverse-word-order)
  - [🪓 Удаление всех цифр из строки (регулярка)](#remove-digits-regex)
  - [🧪 Содержит ли строка только цифры (Character)](#contains-only-digits)
  - [📏 Самое длинное слово в строке](#longest-word-in-string)
  - [🧮 Подсчет частоты слов в строке (Map)](#word-frequency-map)
  - [🔤 Сортировка символов строки по алфавиту](#sort-characters-in-string)
  - [📦 Упаковка одинаковых символов (Run-Length Encoding)](#run-length-encoding)
  - [🪞 Является ли строка зеркальной](#is-mirrored-string)
  - [🔗 Проверка, является ли одна строка ротацией другой](#is-rotation-of-string)
  - [📚 Генерация всех подстрок строки](#generate-all-substrings)
   
- **Коллекции**
  - [🔁 Обмен ключей и значений в HashMap](#swap-keys-values-hashmap)
  - [🗃️ Частота слов в тексте (Map)](#word-frequency-map)
  - [📜 Сортировка HashMap по значениям](#sort-hashmap-by-values)
 
- **Массивы**
  - [🔢 Сортировка массива по возрастанию или убыванию](#sort-array)
  - [📈 Нахождение второго максимального числа в массиве](#second-largest-in-array)
  - [📏 Наибольшая последовательность в массиве](#longest-sequence-in-array)
  - [🔍 Линейный и бинарный поиск в массиве](#linear-binary-search)

- **Стримы (Streams)**
  - [🔄 Фильтрация и сбор элементов списка по условию](#filter-and-collect-list)
  - [📊 Подсчет количества элементов, удовлетворяющих условию](#count-elements-by-condition)
  - [🧮 Суммирование значений поля объектов с использованием стримов](#sum-field-values)
  - [🔤 Преобразование списка строк в список их длин](#map-strings-to-lengths)
  - [📦 Группировка объектов по определённому критерию](#group-by-criteria)
  - [🎯 Нахождение первого элемента, подходящего под условие](#find-first-element)
  - [🧹 Удаление дубликатов из коллекции с помощью стримов](#distinct-elements)
  - [🆚 Проверка, все ли элементы удовлетворяют условию (allMatch)](#all-match-condition)
  - [🔗 Объединение нескольких коллекций в один поток](#concat-streams)
  - [⚡ Преобразование и фильтрация числового диапазона IntStream](#intstream-filter-map)
  - [💡 Преобразование Map в Stream и его обработка](#map-to-stream-processing)
  - [🔍 Поиск максимального и минимального значения через стримы](#find-max-min-stream)
  - [🧩 Преобразование списка объектов в Map по ключу](#list-to-map)
  - [🔢 Сортировка коллекции с помощью Stream.sorted()](#stream-sorted)
  - [⚙️ Параллельная обработка данных с помощью parallelStream](#parallel-stream-processing)


## Строки

### 🔄 Развернуть строку (массив char) <a id="reverse-string-char-array"></a>

```java
public class Main {
    public static void main(String[] args) {
        String str = "Hello, World!";
        
        // Преобразуем строку в массив символов
        char[] charArray = str.toCharArray();
        
        // Создаем пустой массив для хранения результата
        char[] reversedArray = new char[charArray.length];
        
        // Перебираем массив с конца к началу
        for (int i = charArray.length - 1, j = 0; i >= 0; i--, j++) {
            // Записываем символы в обратном порядке
            reversedArray[j] = charArray[i];
        }
        
        // Преобразуем результат обратно в строку и выводим его
        System.out.println(new String(reversedArray));
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🔄 Развернуть строку (цикл с StringBuilder) <a id="reverse-string-stringbuilder"></a>

```java
public class Main {
    public static void main(String[] args) {
        String str = "Hello, World!";
        StringBuilder result = new StringBuilder();
        
        // Проходим по строке с конца к началу
        for (int i = str.length() - 1; i >= 0; i--) {
            // Добавляем каждый символ к StringBuilder
            result.append(str.charAt(i));
        }
        
        // Выводим результат
        System.out.println(result.toString());
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🔄 Развернуть строку (стек Deque) <a id="reverse-string-deque"></a>

```java
import java.util.ArrayDeque;
import java.util.Deque;

public class Main {
    public static void main(String[] args) {
        String str = "Hello, World!";
        
        // Создаем стек для хранения символов строки
        Deque<Character> stack = new ArrayDeque<>();
        
        // Проходим по всем символам строки и помещаем их в стек
        for (char ch : str.toCharArray()) {
            stack.push(ch);
        }
        
        // Создаем StringBuilder для результата
        StringBuilder result = new StringBuilder();
        
        // Извлекаем символы из стека до тех пор, пока он не станет пустым
        while (!stack.isEmpty()) {
            result.append(stack.pop());
        }
        
        // Выводим результат
        System.out.println(result.toString());
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🔥 Развернуть строку (использование рекурсии) <a id="reverse-string-recursion"></a>

```java
public class Main {
    public static void main(String[] args) {
        String str = "Hello, World!";
        
        // Выводим результат вызова рекурсивного метода
        System.out.println(reverseString(str));
    }

    public static String reverseString(String str) {
        // Базовый случай: если строка пустая или состоит из одного символа, вернуть её
        if (str == null || str.length() <= 1) {
            return str;
        }
        
        // Рекурсивный случай: взять последний символ и добавить его к результату от оставшейся строки
        return str.charAt(str.length() - 1) + reverseString(str.substring(0, str.length() - 1));
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🌀 Развернуть строку (рекурсия и лямбда-выражение) <a id="reverse-string-recursion-lambda"></a>

```java
import java.util.function.Function;

public class Main {
    public static void main(String[] args) {
        String str = "Hello, World!";
        
        // Лямбда-выражение для реверса строки
        Function<String, String> reverse = s -> {
            if (s.isEmpty() || s.length() == 1) {
                return s;
            }
            return s.charAt(s.length() - 1) + reverse.apply(s.substring(0, s.length() - 1));
        };
        
        // Выводим результат
        System.out.println(reverse.apply(str));
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🔥 Развернуть строку (чистая рекурсия) <a id="reverse-string-pure-recursion"></a>

```java
public class Main {
    public static void main(String[] args) {
        String str = "Hello, World!";
        System.out.println(reverseString(str, str.length() - 1));
    }

    public static String reverseString(String str, int index) {
        // Базовый случай: если индекс меньше 0, вернуть пустую строку
        if (index < 0) {
            return "";
        }
        
        // Рекурсивно добавляем текущий символ и передаем оставшиеся символы
        return str.charAt(index) + reverseString(str, index - 1);
    }
}
```

[🔼 К содержанию](#Содержание)

---

### ✅ Проверка на палиндром <a id="check-palindrome"></a>

```java
public class Main {
    public static void main(String[] args) {
        String str = "madam";
        
        // Проверяем, является ли строка палиндромом
        boolean isPalindrome = checkPalindrome(str);
        
        // Выводим результат
        System.out.println("Строка \"" + str + "\" является палиндромом: " + isPalindrome);
    }

    public static boolean checkPalindrome(String str) {
        // Определяем длину строки
        int length = str.length();
        
        // Проходим по строке от начала и конца одновременно
        for (int i = 0; i < length / 2; i++) {
            // Сравниваем символы на противоположных концах
            if (str.charAt(i) != str.charAt(length - 1 - i)) {
                // Если символы не совпадают, возвращаем false
                return false;
            }
        }
        
        // Если все символы совпадают, возвращаем true
        return true;
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🔥 Подсчет вхождений символа в строке (Map) <a id="count-char-occurrences-map"></a>

```java
import java.util.HashMap;
import java.util.Map;

public class Main {
    public static void main(String[] args) {
        String str = "Hello, World!";
        
        // Подсчитываем вхождения символов и выводим результат
        Map<Character, Integer> occurrences = countOccurrences(str);
        System.out.println(occurrences);
    }

    public static Map<Character, Integer> countOccurrences(String str) {
        // Создаем HashMap для хранения символов и их частоты
        Map<Character, Integer> map = new HashMap<>();
        
        // Проходим по каждому символу строки
        for (char ch : str.toCharArray()) {
            // Если символ уже есть в map, увеличиваем значение на 1
            if (map.containsKey(ch)) {
                map.put(ch, map.get(ch) + 1);
            } else {
                // Если символа еще нет, добавляем его с частотой 1
                map.put(ch, 1);
            }
        }
        
        // Возвращаем результат
        return map;
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 📊 Подсчет вхождений символа в строке (простой) <a id="count-char-occurrences-simple"></a>

```java
public class Main {
    public static void main(String[] args) {
        String str = "Hello, World!";
        char target = 'o';
        
        // Подсчитываем количество вхождений символа 'o'
        int count = countOccurrences(str, target);
        
        // Выводим результат
        System.out.println("Символ '" + target + "' встречается " + count + " раз(а).");
    }

    public static int countOccurrences(String str, char target) {
        int count = 0;
        
        // Проходим по строке символ за символом
        for (int i = 0; i < str.length(); i++) {
            if (str.charAt(i) == target) {
                count++; // Увеличиваем счетчик, если нашли нужный символ
            }
        }
        
        // Возвращаем общее количество вхождений
        return count;
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🔥 Удаление дубликатов символов из строки (Set) <a id="remove-duplicates-set"></a>

```java
import java.util.LinkedHashSet;
import java.util.Set;

public class Main {
    public static void main(String[] args) {
        String str = "Hello, World!";
        
        // Удаляем дубликаты и выводим результат
        String result = removeDuplicates(str);
        System.out.println("Строка без дубликатов: " + result);
    }

    public static String removeDuplicates(String str) {
        // Создаем Set для хранения уникальных символов
        Set<Character> seen = new LinkedHashSet<>();
        
        // StringBuilder для хранения результата
        StringBuilder result = new StringBuilder();
        
        // Проходим по строке
        for (char ch : str.toCharArray()) {
            // Если символ встречается впервые, добавляем его в результат
            if (seen.add(ch)) {
                result.append(ch);
            }
        }
        
        // Возвращаем строку без дубликатов
        return result.toString();
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🧹 Удаление дубликатов символов из строки (простой) <a id="remove-duplicates-simple"></a>

```java
public class Main {
    public static void main(String[] args) {
        String str = "Hello, World!";
        
        // Удаляем дубликаты и выводим результат
        String result = removeDuplicates(str);
        System.out.println("Строка без дубликатов: " + result);
    }

    public static String removeDuplicates(String str) {
        StringBuilder result = new StringBuilder();
        
        // Проходим по каждому символу строки
        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);
            
            // Если символ еще не добавлен в результат, добавляем его
            if (result.indexOf(String.valueOf(ch)) == -1) {
                result.append(ch);
            }
        }
        
        // Возвращаем строку без дубликатов
        return result.toString();
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🔄 Замена символов в строке <a id="replace-characters"></a>

```java
public class Main {
    public static void main(String[] args) {
        String str = "Hello, World!";
        char oldChar = 'o';
        char newChar = 'a';
        
        // Заменяем символ и выводим результат
        String result = replaceCharacters(str, oldChar, newChar);
        System.out.println("Результат: " + result);
    }

    public static String replaceCharacters(String str, char oldChar, char newChar) {
        StringBuilder result = new StringBuilder();
        
        // Проходим по каждому символу строки
        for (int i = 0; i < str.length(); i++) {
            char currentChar = str.charAt(i);
            
            // Если текущий символ совпадает с заменяемым, добавляем новый символ
            if (currentChar == oldChar) {
                result.append(newChar);
            } else {
                // Иначе добавляем текущий символ без изменений
                result.append(currentChar);
            }
        }
        
        // Возвращаем измененную строку
        return result.toString();
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 📌 Разделение строки на числа и буквы, подсчет суммы чисел <a id="split-string-sum-numbers"></a>

```java
public class Main {
    public static void main(String[] args) {
        String str = "abc12def34ghi56";
        
        // Разделяем строку и подсчитываем сумму чисел
        int sum = sumNumbersInString(str);
        System.out.println("Сумма чисел в строке: " + sum);
    }

    public static int sumNumbersInString(String str) {
        int sum = 0; // Переменная для хранения суммы чисел
        StringBuilder number = new StringBuilder(); // Для накопления цифр
        
        // Проходим по каждому символу строки
        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);
            
            // Если символ является цифрой, добавляем его к number
            if (Character.isDigit(ch)) {
                number.append(ch);
            } else {
                // Если символ не цифра и у нас есть накопленное число, добавляем его к сумме
                if (number.length() > 0) {
                    sum += Integer.parseInt(number.toString());
                    number.setLength(0); // Очищаем number для нового числа
                }
            }
        }
        
        // Добавляем последнее накопленное число, если оно есть
        if (number.length() > 0) {
            sum += Integer.parseInt(number.toString());
        }
        
        // Возвращаем общую сумму найденных чисел
        return sum;
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 📚 Перестановки строки (рекурсия) <a id="string-permutations-recursion"></a>

```java
public class Main {
    public static void main(String[] args) {
        String str = "ABC";
        
        // Вызываем метод для вывода всех перестановок
        generatePermutations("", str);
    }

    public static void generatePermutations(String prefix, String str) {
        int n = str.length();
        
        // Если строка пустая, выводим текущую перестановку
        if (n == 0) {
            System.out.println(prefix);
        } else {
            // Проходим по всем символам строки
            for (int i = 0; i < n; i++) {
                // Рекурсивно создаем новые комбинации, исключая текущий символ
                generatePermutations(prefix + str.charAt(i), 
                                     str.substring(0, i) + str.substring(i + 1));
            }
        }
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🧩 Наибольшая общая подстрока двух строк <a id="longest-common-substring"></a>

```java
public class Main {
    public static void main(String[] args) {
        String str1 = "abcdef";
        String str2 = "zabcf";
        
        // Находим и выводим наибольшую общую подстроку
        String result = longestCommonSubstring(str1, str2);
        System.out.println("Наибольшая общая подстрока: " + result);
    }

    public static String longestCommonSubstring(String str1, String str2) {
        int maxLength = 0; // Максимальная длина найденной подстроки
        int endIndex = 0;   // Индекс окончания найденной подстроки
        int[][] dp = new int[str1.length() + 1][str2.length() + 1];
        
        // Проходим по двум строкам
        for (int i = 1; i <= str1.length(); i++) {
            for (int j = 1; j <= str2.length(); j++) {
                if (str1.charAt(i - 1) == str2.charAt(j - 1)) {
                    dp[i][j] = dp[i - 1][j - 1] + 1; // Если символы совпадают, увеличиваем длину текущей подстроки
                    
                    if (dp[i][j] > maxLength) { // Обновляем максимальную длину
                        maxLength = dp[i][j];
                        endIndex = i; // Запоминаем текущий индекс окончания
                    }
                }
            }
        }
        
        // Возвращаем найденную подстроку
        return str1.substring(endIndex - maxLength, endIndex);
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🔍 Проверка на уникальность символов в строке (Set) <a id="is-unique-characters"></a>

```java
import java.util.HashSet;
import java.util.Set;

public class Main {

    public static boolean isUnique(String input) {
        Set<Character> seen = new HashSet<>();
        for (char c : input.toCharArray()) {
            if (!seen.add(c)) {
                return false; // символ уже встречался
            }
        }
        return true; // все символы уникальны
    }

    public static void main(String[] args) {
        System.out.println(isUnique("abcdef"));   // true
        System.out.println(isUnique("hello"));    // false
    }
}
```
[🔼 К содержанию](#Содержание)

---

### 🆚 Являются ли строки анаграммами <a id="check-anagram"></a>

```java
import java.util.Arrays;

public class Main {

    public static boolean isAnagram(String s1, String s2) {
        // Убираем пробелы и приводим к нижнему регистру
        s1 = s1.replaceAll("\\s+", "").toLowerCase();
        s2 = s2.replaceAll("\\s+", "").toLowerCase();

        // Если длины не совпадают — точно не анаграммы
        if (s1.length() != s2.length()) {
            return false;
        }

        // Сортируем символы и сравниваем
        char[] a1 = s1.toCharArray();
        char[] a2 = s2.toCharArray();
        Arrays.sort(a1);
        Arrays.sort(a2);

        return Arrays.equals(a1, a2);
    }

    public static void main(String[] args) {
        System.out.println(isAnagram("listen", "silent"));     // true
        System.out.println(isAnagram("triangle", "integral")); // true
        System.out.println(isAnagram("hello", "world"));       // false
    }
}

```

[🔼 К содержанию](#Содержание)

---

### 🔢 Подсчет количества слов в строке <a id="count-words-in-string"></a>

```java
public class Main {

    public static int countWords(String input) {
        if (input == null || input.trim().isEmpty()) {
            return 0;
        }

        // Разделение по одному или нескольким пробелам
        String[] words = input.trim().split("\\s+");
        return words.length;
    }

    public static void main(String[] args) {
        System.out.println(countWords("Java is fun"));             // 3
        System.out.println(countWords("   Hello    world   "));    // 2
        System.out.println(countWords(""));                        // 0
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🧵 Удаление всех пробелов из строки <a id="remove-all-whitespaces"></a>

```java
public class Main {

    public static String removeWhitespaces(String input) {
        return input.replaceAll("\\s+", "");
    }

    public static void main(String[] args) {
        System.out.println(removeWhitespaces("Java is fun"));         // "Javaisfun"
        System.out.println(removeWhitespaces("   Hello   world "));   // "Helloworld"
        System.out.println(removeWhitespaces(""));                    // ""
    }
}

```

[🔼 К содержанию](#Содержание)

---

### 📐 Является ли строка перестановкой другой <a id="is-permutation"></a>

```java
import java.util.Arrays;

public class Main {

    public static boolean isPermutation(String s1, String s2) {
        if (s1 == null || s2 == null) return false;
        if (s1.length() != s2.length()) return false;

        char[] a1 = s1.toCharArray();
        char[] a2 = s2.toCharArray();

        Arrays.sort(a1);
        Arrays.sort(a2);

        return Arrays.equals(a1, a2);
    }

    public static void main(String[] args) {
        System.out.println(isPermutation("abc", "bca"));   // true
        System.out.println(isPermutation("abc", "abcd"));  // false
        System.out.println(isPermutation("abc", "def"));   // false
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🔄 Инвертировать порядок слов в строке <a id="reverse-word-order"></a>

```java
public class Main {

    public static String reverseWordOrder(String input) {
        if (input == null || input.trim().isEmpty()) {
            return input;
        }

        String[] words = input.trim().split("\\s+");
        StringBuilder reversed = new StringBuilder();

        for (int i = words.length - 1; i >= 0; i--) {
            reversed.append(words[i]);
            if (i != 0) {
                reversed.append(" ");
            }
        }

        return reversed.toString();
    }

    public static void main(String[] args) {
        System.out.println(reverseWordOrder("Java is fun"));          // "fun is Java"
        System.out.println(reverseWordOrder("  Hello   world  "));    // "world Hello"
        System.out.println(reverseWordOrder("single"));               // "single"
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🪓 Удаление всех цифр из строки (регулярка) <a id="remove-digits-regex"></a>

```java
public class Main {

    public static String removeDigits(String input) {
        if (input == null) return null;
        return input.replaceAll("\\d", "");
    }

    public static void main(String[] args) {
        System.out.println(removeDigits("abc123def456"));  // "abcdef"
        System.out.println(removeDigits("2025 год"));      // " год"
        System.out.println(removeDigits("no digits"));     // "no digits"
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🧪 Содержит ли строка только цифры (Character) <a id="contains-only-digits"></a>

```java
public class Main {

    public static boolean containsOnlyDigits(String input) {
        if (input == null || input.isEmpty()) return false;
        for (char c : input.toCharArray()) {
            if (!Character.isDigit(c)) {
                return false;
            }
        }
        return true;
    }

    public static void main(String[] args) {
        System.out.println(containsOnlyDigits("123456"));   // true
        System.out.println(containsOnlyDigits("123a456"));  // false
        System.out.println(containsOnlyDigits(""));         // false
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 📏 Самое длинное слово в строке <a id="longest-word-in-string"></a>

```java
public class Main {

    public static String longestWord(String input) {
        if (input == null || input.trim().isEmpty()) {
            return "";
        }

        String[] words = input.trim().split("\\s+");
        String longest = "";

        for (String word : words) {
            if (word.length() > longest.length()) {
                longest = word;
            }
        }

        return longest;
    }

    public static void main(String[] args) {
        System.out.println(longestWord("Java is awesome"));         // "awesome"
        System.out.println(longestWord("   hello world "));          // "hello"
        System.out.println(longestWord(""));                         // ""
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🧮 Подсчет частоты слов в строке (Map) <a id="word-frequency-map"></a>

```java

```

[🔼 К содержанию](#Содержание)

---

### 🔤 Сортировка символов строки по алфавиту <a id="sort-characters-in-string"></a>

```java

```

[🔼 К содержанию](#Содержание)

---

### 📦 Упаковка одинаковых символов (Run-Length Encoding) <a id="run-length-encoding"></a>

```java

```

[🔼 К содержанию](#Содержание)

---

### 🪞 Является ли строка зеркальной <a id="is-mirrored-string"></a>

```java

```

[🔼 К содержанию](#Содержание)

---

### 🔗 Проверка, является ли одна строка ротацией другой <a id="is-rotation-of-string"></a>

```java

```

[🔼 К содержанию](#Содержание)

---

### 📚 Генерация всех подстрок строки <a id="generate-all-substrings"></a>

```java

```

[🔼 К содержанию](#Содержание)

---


## Коллекции

### 🔁 Обмен ключей и значений в HashMap <a id="swap-keys-values-hashmap"></a>

```java
import java.util.HashMap;
import java.util.Map;

public class Main {
    public static void main(String[] args) {
        // Исходный HashMap
        Map<String, Integer> originalMap = new HashMap<>();
        originalMap.put("One", 1);
        originalMap.put("Two", 2);
        originalMap.put("Three", 3);
        
        // Вызываем метод для обмена ключей и значений
        Map<Integer, String> swappedMap = swapKeysAndValues(originalMap);
        
        // Выводим результат
        System.out.println("Перевернутый HashMap: " + swappedMap);
    }

    public static <K, V> Map<V, K> swapKeysAndValues(Map<K, V> map) {
        // Создаем новый HashMap для хранения перевернутых значений
        Map<V, K> swappedMap = new HashMap<>();
        
        // Проходим по всем записям исходной карты
        for (Map.Entry<K, V> entry : map.entrySet()) {
            // Добавляем значение в качестве ключа и ключ в качестве значения
            swappedMap.put(entry.getValue(), entry.getKey());
        }
        
        // Возвращаем перевернутую карту
        return swappedMap;
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🗃️ Частота слов в тексте (Map) <a id="word-frequency-map"></a>

```java
import java.util.HashMap;
import java.util.Map;

public class Main {
    public static void main(String[] args) {
        String text = "hello world hello everyone";
        
        // Подсчитываем частоту слов в тексте
        Map<String, Integer> wordFrequency = countWordFrequency(text);
        
        // Выводим результат
        System.out.println("Частота слов: " + wordFrequency);
    }

    public static Map<String, Integer> countWordFrequency(String text) {
        // Разделяем текст на слова
        String[] words = text.split(" ");
        
        // Создаем карту для хранения частоты слов
        Map<String, Integer> wordCount = new HashMap<>();
        
        // Проходим по всем словам и считаем их частоту
        for (String word : words) {
            wordCount.put(word, wordCount.getOrDefault(word, 0) + 1);
        }
        
        // Возвращаем результат
        return wordCount;
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 📜 Сортировка HashMap по значениям <a id="sort-hashmap-by-values"></a>

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        // Исходный HashMap
        Map<String, Integer> map = new HashMap<>();
        map.put("Apple", 3);
        map.put("Banana", 1);
        map.put("Orange", 2);
        
        // Сортируем HashMap по значениям
        Map<String, Integer> sortedMap = sortByValue(map);
        
        // Выводим результат
        System.out.println("Отсортированная карта: " + sortedMap);
    }

    public static Map<String, Integer> sortByValue(Map<String, Integer> map) {
        // Создаем список для сортировки
        List<Map.Entry<String, Integer>> list = new ArrayList<>(map.entrySet());
        
        // Сортируем список по значениям
        list.sort(Map.Entry.comparingByValue());
        
        // Создаем новую карту для хранения отсортированных значений
        Map<String, Integer> sortedMap = new LinkedHashMap<>();
        
        // Копируем отсортированные записи в новую карту
        for (Map.Entry<String, Integer> entry : list) {
            sortedMap.put(entry.getKey(), entry.getValue());
        }
        
        // Возвращаем отсортированную карту
        return sortedMap;
    }
}
```

[🔼 К содержанию](#Содержание)

---

## Массивы

### 🔢 Сортировка массива по возрастанию или убыванию <a id="sort-array"></a>

```java
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] array = {5, 2, 9, 1, 5, 6};
        
        // Сортируем массив по возрастанию
        int[] ascendingArray = sortArray(array, true);
        System.out.println("Сортировка по возрастанию: " + Arrays.toString(ascendingArray));
        
        // Сортируем массив по убыванию
        int[] descendingArray = sortArray(array, false);
        System.out.println("Сортировка по убыванию: " + Arrays.toString(descendingArray));
    }

    public static int[] sortArray(int[] array, boolean ascending) {
        // Создаем копию массива, чтобы не изменять оригинальный
        int[] sortedArray = Arrays.copyOf(array, array.length);
        
        // Реализуем пузырьковую сортировку
        for (int i = 0; i < sortedArray.length - 1; i++) {
            for (int j = 0; j < sortedArray.length - 1 - i; j++) {
                // Сравниваем соседние элементы
                if ((ascending && sortedArray[j] > sortedArray[j + 1]) || 
                    (!ascending && sortedArray[j] < sortedArray[j + 1])) {
                    
                    // Меняем элементы местами
                    int temp = sortedArray[j];
                    sortedArray[j] = sortedArray[j + 1];
                    sortedArray[j + 1] = temp;
                }
            }
        }
        
        // Возвращаем отсортированный массив
        return sortedArray;
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 📈 Нахождение второго максимального числа в массиве <a id="second-largest-in-array"></a>

```java
public class Main {
    public static void main(String[] args) {
        int[] array = {5, 2, 9, 1, 5, 6};
        
        // Находим второй по величине элемент
        int secondLargest = findSecondLargest(array);
        
        // Выводим результат
        System.out.println("Второй по величине элемент: " + secondLargest);
    }

    public static int findSecondLargest(int[] array) {
        if (array.length < 2) {
            throw new IllegalArgumentException("Массив должен содержать минимум два элемента.");
        }

        int largest = Integer.MIN_VALUE;
        int secondLargest = Integer.MIN_VALUE;

        // Перебираем все элементы массива
        for (int num : array) {
            if (num > largest) {
                // Обновляем значения largest и secondLargest
                secondLargest = largest;
                largest = num;
            } else if (num > secondLargest && num != largest) {
                // Обновляем значение secondLargest, если оно меньше текущего элемента
                secondLargest = num;
            }
        }
        
        // Возвращаем найденный элемент
        return secondLargest;
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 📏 Наибольшая последовательность в массиве <a id="longest-sequence-in-array"></a>

```java
public class Main {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 5, 6, 7, 8};
        
        // Находим и выводим наибольшую последовательность
        int longestSequence = findLongestSequence(array);
        System.out.println("Длина наибольшей последовательности: " + longestSequence);
    }

    public static int findLongestSequence(int[] array) {
        int maxLength = 1;
        int currentLength = 1;
        
        // Проходим по массиву
        for (int i = 1; i < array.length; i++) {
            // Если текущий элемент больше предыдущего, увеличиваем длину последовательности
            if (array[i] == array[i - 1] + 1) {
                currentLength++;
            } else {
                // Если последовательность прервана, обновляем максимальную длину
                maxLength = Math.max(maxLength, currentLength);
                currentLength = 1;
            }
        }
        
        // Возвращаем максимальную длину последовательности
        return Math.max(maxLength, currentLength);
    }
}
```

[🔼 К содержанию](#Содержание)

---

### 🔍 Линейный и бинарный поиск в массиве <a id="linear-binary-search"></a>

```java
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
        
        // Линейный поиск
        int linearResult = linearSearch(array, 5);
        System.out.println("Линейный поиск: индекс 5 - " + linearResult);
        
        // Бинарный поиск
        int binaryResult = binarySearch(array, 5);
        System.out.println("Бинарный поиск: индекс 5 - " + binaryResult);
    }

    public static int linearSearch(int[] array, int target) {
        // Проходим по массиву и ищем элемент
        for (int i = 0; i < array.length; i++) {
            if (array[i] == target) {
                return i; // Если нашли, возвращаем индекс
            }
        }
        return -1; // Если не нашли, возвращаем -1
    }

    public static int binarySearch(int[] array, int target) {
        int left = 0;
        int right = array.length - 1;
        
        // Пока левая граница не превысит правую
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (array[mid] == target) {
                return mid; // Если нашли, возвращаем индекс
            } else if (array[mid] < target) {
                left = mid + 1; // Ищем справа
            } else {
                right = mid - 1; // Ищем слева
            }
        }
        
        return -1; // Если не нашли, возвращаем -1
    }
}
```

[🔼 К содержанию](#Содержание)

---

## Стримы (Streams)

### 🔄 Фильтрация и сбор элементов списка по условию <a id="filter-and-collect-list"></a>  

```java
import java.util.List;
import java.util.stream.Collectors;

public class FilterExample {
    public static void main(String[] args) {
        List<String> names = List.of("Anna", "Bob", "Alice", "Mike", "Amanda");

        // Фильтрация: выбрать имена, начинающиеся с буквы 'A'
        List<String> filteredNames = names.stream()
            .filter(name -> name.startsWith("A"))
            .collect(Collectors.toList());

        System.out.println(filteredNames); // Выведет: [Anna, Alice, Amanda]
    }
}
```

[🔼 К содержанию](#Содержание)  
---

### 📊 Подсчет количества элементов, удовлетворяющих условию <a id="count-elements-by-condition"></a> 

```java
import java.util.List;

public class CountExample {
    public static void main(String[] args) {
        List<Integer> numbers = List.of(1, 5, 8, 10, 3, 7);

        // Подсчитать количество чисел больше 5
        long count = numbers.stream()
            .filter(n -> n > 5)
            .count();

        System.out.println("Количество чисел больше 5: " + count); // Выведет: 3
    }
}
```

[🔼 К содержанию](#Содержание)  

---

### 🧮 Суммирование значений поля объектов с использованием стримов <a id="sum-field-values"></a>  

```java
import java.util.List;

class Product {
    private String name;
    private int price;

    public Product(String name, int price) {
        this.name = name;
        this.price = price;
    }

    public int getPrice() {
        return price;
    }
}

public class SumExample {
    public static void main(String[] args) {
        List<Product> products = List.of(
            new Product("Book", 100),
            new Product("Pen", 20),
            new Product("Notebook", 50)
        );

        int totalPrice = products.stream()
            .mapToInt(Product::getPrice)
            .sum();

        System.out.println("Общая сумма цен: " + totalPrice); // Выведет: 170
    }
}
```

[🔼 К содержанию](#Содержание)  

---

### 🔤 Преобразование списка строк в список их длин <a id="map-strings-to-lengths"></a>  

```java

```

[🔼 К содержанию](#Содержание)  

---

### 📦 Группировка объектов по определённому критерию <a id="group-by-criteria"></a>  

```java

```

[🔼 К содержанию](#Содержание)  

---

### 🎯 Нахождение первого элемента, подходящего под условие <a id="find-first-element"></a>  

```java

```

[🔼 К содержанию](#Содержание)  

---

### 🧹 Удаление дубликатов из коллекции с помощью стримов <a id="distinct-elements"></a> 

```java

```

[🔼 К содержанию](#Содержание)  

---

### 🆚 Проверка, все ли элементы удовлетворяют условию (allMatch) <a id="all-match-condition"></a> 

```java

```

[🔼 К содержанию](#Содержание) 

---

### 🔗 Объединение нескольких коллекций в один поток <a id="concat-streams"></a>  

```java

```

[🔼 К содержанию](#Содержание)  

---

### ⚡ Преобразование и фильтрация числового диапазона IntStream <a id="intstream-filter-map"></a> 

```java

```

[🔼 К содержанию](#Содержание) 

---

### 💡 Преобразование Map в Stream и его обработка <a id="map-to-stream-processing"></a>  

```java

```

[🔼 К содержанию](#Содержание)  

---

### 🔍 Поиск максимального и минимального значения через стримы <a id="find-max-min-stream"></a> 

```java

```

[🔼 К содержанию](#Содержание)  

---

### 🧩 Преобразование списка объектов в Map по ключу <a id="list-to-map"></a>  

```java

```

[🔼 К содержанию](#Содержание) 

---

### 🔢 Сортировка коллекции с помощью Stream.sorted() <a id="stream-sorted"></a>  

```java

```

[🔼 К содержанию](#Содержание) 

---

### ⚙️ Параллельная обработка данных с помощью parallelStream <a id="parallel-stream-processing"></a> 

```java

```

[🔼 К содержанию](#Содержание)

---

