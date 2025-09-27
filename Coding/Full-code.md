# Содержание <a name="contents"></a>                         
 
1. [Нахождение максимального числа в массиве](#max)
2. [Удаление дубликатов из массива](#unique)
3. [Проверка, является ли строка палиндромом](#palindrome)
4. [Подсчёт количества уникальных элементов в массиве](#unique-count)
5. [Преобразование массива в строку через разделитель](#array-to-string)
6. [Проверка, содержит ли массив определённое значение](#contains)
7. [Нахождение суммы всех элементов массива](#sum)
8. [Фильтрация чётных чисел из массива](#evens)
9. [Поиск индекса минимального элемента в массиве](#min-index)
10. [Объединение двух массивов без дубликатов](#merge-arrays)
11. [Переворот строки](#reverse-string)
12. [Проверка, являются ли две строки анаграммами](#anagrams)


## 1. Нахождение максимального числа в массиве <a name="max"></a>

```java
int max = Arrays.stream(new int[]{1, 5, 3, 9}).max().getAsInt();
```
Максимальное число: Используется Arrays.stream для преобразования массива в поток и метод max() для поиска максимального значения.  

[Вернуться к оглавлению](#contents)

--- 

## 2. Удаление дубликатов из массива <a name="unique"></a>

```java
List<Integer> unique = Arrays.stream(new int[]{1, 2, 2, 3, 4})
                             .distinct()
                             .boxed()
                             .collect(Collectors.toList());
```
Удаление дубликатов: Метод distinct() удаляет повторяющиеся элементы, а boxed() преобразует примитивные типы в объекты.  

[Вернуться к оглавлению](#contents)

---

## 3. Проверка, является ли строка палиндромом <a name="palindrome"></a>

```java
boolean isPalindrome = new StringBuilder("racecar").reverse().toString().equals("racecar");
```
Палиндром: Строка разворачивается с помощью StringBuilder.reverse(), затем сравнивается с исходной.  

[Вернуться к оглавлению](#contents)

---

## 4. Подсчёт количества уникальных элементов в массиве <a name="unique-count"></a>

```java
long uniqueCount = Arrays.stream(new int[]{1, 2, 2, 3, 4}).distinct().count();
```
Количество уникальных элементов: Используется distinct() для удаления дубликатов и count() для подсчёта элементов.  

[Вернуться к оглавлению](#contents)

---

## 5. Преобразование массива в строку через разделитель <a name="array-to-string"></a>

```java
String result = String.join(", ", Arrays.stream(new int[]{1, 2, 3}).mapToObj(String::valueOf).toArray(String[]::new));
```
Преобразование массива в строку: String.join() объединяет элементы массива через заданный разделитель.  

[Вернуться к оглавлению](#contents)

---

## 6. Проверка, содержит ли массив определённое значение <a name="contains"></a>

```java
boolean contains = Arrays.stream(new int[]{1, 2, 3, 4}).anyMatch(n -> n == 3);
```
Проверка наличия элемента: Метод anyMatch() проверяет, удовлетворяет ли хотя бы один элемент условию.  

[Вернуться к оглавлению](#contents)

---
 
## 7. Нахождение суммы всех элементов массива <a name="sum"></a>

```java
int sum = Arrays.stream(new int[]{1, 2, 3, 4}).sum();
```
Сумма элементов: Метод sum() вычисляет сумму всех элементов массива.  

[Вернуться к оглавлению](#contents)

---

## 8. Фильтрация чётных чисел из массива <a name="evens"></a>

```java
List<Integer> evens = Arrays.stream(new int[]{1, 2, 3, 4, 5})
                            .filter(n -> n % 2 == 0)
                            .boxed()
                            .collect(Collectors.toList());
```
Фильтрация чётных чисел: Используется filter() для отбора элементов, удовлетворяющих условию.

[Вернуться к оглавлению](#contents)

---

## 9. Поиск индекса минимального элемента в массиве <a name="min-index"></a>

```java
int minIndex = IntStream.range(0, new int[]{5, 1, 3, 2}.length)
                        .reduce((i, j) -> new int[]{5, 1, 3, 2}[i] < new int[]{5, 1, 3, 2}[j] ? i : j)
                        .getAsInt();
```
Индекс минимального элемента: Используется IntStream.range() для создания потока индексов и reduce() для поиска минимального элемента.

[Вернуться к оглавлению](#contents)

---

## 10. Объединение двух массивов без дубликатов <a name="merge-arrays"></a>

```java
List<Integer> merged = Arrays.stream(new int[]{1, 2, 3})
                             .boxed()
                             .collect(Collectors.toSet())
                             .addAll(Arrays.stream(new int[]{3, 4, 5}).boxed().collect(Collectors.toSet()))
                             .stream()
                             .toList();
```

Объединение массивов: Используются множества (Set) для автоматического удаления дубликатов.

[Вернуться к оглавлению](#contents)

---

## 11. Переворот строки <a name="reverse-string"></a>
 
```java
String reversed = new StringBuilder("hello").reverse().toString();
```
Переворот строки: Строка разворачивается с помощью StringBuilder.reverse().

[Вернуться к оглавлению](#contents)

---

## 12. Проверка, являются ли две строки анаграммами <a name="anagrams"></a>

```java
boolean areAnagrams = "listen".chars().sorted().toArray()
                              .deepEquals("silent".chars().sorted().toArray());
```

Анаграммы: Символы строк сортируются, и их массивы сравниваются.

[Вернуться к оглавлению](#contents)

---

