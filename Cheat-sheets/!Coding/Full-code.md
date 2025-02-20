## 1. Нахождение максимального числа в массиве

```java
int max = Arrays.stream(new int[]{1, 5, 3, 9}).max().getAsInt();
```
Максимальное число: Используется Arrays.stream для преобразования массива в поток и метод max() для поиска максимального значения.  

---

## 2. Удаление дубликатов из массива

```java
List<Integer> unique = Arrays.stream(new int[]{1, 2, 2, 3, 4})
                             .distinct()
                             .boxed()
                             .collect(Collectors.toList());
```
Удаление дубликатов: Метод distinct() удаляет повторяющиеся элементы, а boxed() преобразует примитивные типы в объекты.  

---

## 3. Проверка, является ли строка палиндромом

```java
boolean isPalindrome = new StringBuilder("racecar").reverse().toString().equals("racecar");
```
Палиндром: Строка разворачивается с помощью StringBuilder.reverse(), затем сравнивается с исходной.  

---

4. Подсчёт количества уникальных элементов в массиве

```java
long uniqueCount = Arrays.stream(new int[]{1, 2, 2, 3, 4}).distinct().count();
```
Количество уникальных элементов: Используется distinct() для удаления дубликатов и count() для подсчёта элементов.  

---

5. Преобразование массива в строку через разделитель

```java
String result = String.join(", ", Arrays.stream(new int[]{1, 2, 3}).mapToObj(String::valueOf).toArray(String[]::new));
```
Преобразование массива в строку: String.join() объединяет элементы массива через заданный разделитель.  

---

6. Проверка, содержит ли массив определённое значение

```java
boolean contains = Arrays.stream(new int[]{1, 2, 3, 4}).anyMatch(n -> n == 3);
```
Проверка наличия элемента: Метод anyMatch() проверяет, удовлетворяет ли хотя бы один элемент условию.  

---

7. Нахождение суммы всех элементов массива

```java
int sum = Arrays.stream(new int[]{1, 2, 3, 4}).sum();
```
Сумма элементов: Метод sum() вычисляет сумму всех элементов массива.  

---

8. Фильтрация чётных чисел из массива

```java
List<Integer> evens = Arrays.stream(new int[]{1, 2, 3, 4, 5})
                            .filter(n -> n % 2 == 0)
                            .boxed()
                            .collect(Collectors.toList());
```
Фильтрация чётных чисел: Используется filter() для отбора элементов, удовлетворяющих условию.

---

9. Поиск индекса минимального элемента в массиве

```java
int minIndex = IntStream.range(0, new int[]{5, 1, 3, 2}.length)
                        .reduce((i, j) -> new int[]{5, 1, 3, 2}[i] < new int[]{5, 1, 3, 2}[j] ? i : j)
                        .getAsInt();
```
Индекс минимального элемента: Используется IntStream.range() для создания потока индексов и reduce() для поиска минимального элемента.

---

10. Объединение двух массивов без дубликатов

```java
List<Integer> merged = Arrays.stream(new int[]{1, 2, 3})
                             .boxed()
                             .collect(Collectors.toSet())
                             .addAll(Arrays.stream(new int[]{3, 4, 5}).boxed().collect(Collectors.toSet()))
                             .stream()
                             .toList();
```

Объединение массивов: Используются множества (Set) для автоматического удаления дубликатов.

---

11. Переворот строки

```java
String reversed = new StringBuilder("hello").reverse().toString();
```
Переворот строки: Строка разворачивается с помощью StringBuilder.reverse().

---

12. Проверка, являются ли две строки анаграммами

```java
boolean areAnagrams = "listen".chars().sorted().toArray()
                              .deepEquals("silent".chars().sorted().toArray());
```

Анаграммы: Символы строк сортируются, и их массивы сравниваются.

---
