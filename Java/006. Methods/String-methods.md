# Строковые Методы в Java

Строковые методы в Java предоставляют различные способы манипуляции и обработки строк. Класс `String` в Java включает множество методов, которые позволяют работать с текстовыми данными.

## Основные методы класса `String`

1. **`charAt(int index)`**: Возвращает символ на указанной позиции в строке.
2. **`compareTo(String anotherString)`**: Сравнивает текущую строку с другой строкой лексикографически.
3. **`concat(String str)`**: Объединяет текущую строку с другой строкой.
4. **`contains(CharSequence sequence)`**: Проверяет, содержит ли текущая строка указанную последовательность символов.
5. **`endsWith(String suffix)`**: Проверяет, заканчивается ли текущая строка указанной подстрокой.
6. **`equals(Object anObject)`**: Сравнивает текущую строку с указанным объектом на равенство.
7. **`equalsIgnoreCase(String anotherString)`**: Сравнивает текущую строку с другой строкой, игнорируя регистр символов.
8. **`format(String format, Object... args)`**: Форматирует строку с использованием указанного формата и аргументов.
9. **`indexOf(String str)`**: Возвращает индекс первого вхождения указанной подстроки в строке.
10. **`isEmpty()`**: Проверяет, является ли текущая строка пустой.
11. **`lastIndexOf(String str)`**: Возвращает индекс последнего вхождения указанной подстроки в строке.
12. **`length()`**: Возвращает длину текущей строки.
13. **`replace(CharSequence target, CharSequence replacement)`**: Заменяет все вхождения указанной последовательности символов на другую.
14. **`split(String regex)`**: Разделяет текущую строку на массив строк, используя указанный регулярное выражение в качестве разделителя.
15. **`startsWith(String prefix)`**: Проверяет, начинается ли текущая строка с указанного префикса.
16. **`substring(int beginIndex)`**: Возвращает подстроку, начиная с указанного индекса до конца строки.
17. **`substring(int beginIndex, int endIndex)`**: Возвращает подстроку от указанного начального индекса до конечного индекса.
18. **`toLowerCase()`**: Преобразует все символы текущей строки в нижний регистр.
19. **`toUpperCase()`**: Преобразует все символы текущей строки в верхний регистр.
20. **`trim()`**: Удаляет начальные и конечные пробелы из строки.

## Дополнительные методы

1. **`matches(String regex)`**: Проверяет, соответствует ли текущая строка указанному регулярному выражению.
2. **`replaceAll(String regex, String replacement)`**: Заменяет все подстроки, которые соответствуют указанному регулярному выражению, на указанную строку замены.
3. **`replaceFirst(String regex, String replacement)`**: Заменяет первое вхождение подстроки, соответствующей указанному регулярному выражению, на указанную строку замены.
4. **`toCharArray()`**: Преобразует текущую строку в массив символов.
5. **`valueOf(Object obj)`**: Возвращает строковое представление объекта.

Методы класса `String` позволяют эффективно выполнять различные операции с текстовыми данными, такие как сравнение, поиск, замена и форматирование. Использование этих методов способствует удобному и эффективному управлению строками в Java.
