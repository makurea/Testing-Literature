# Стеки

Стек — это абстрактная структура данных, работающая по принципу LIFO (Last In, First Out), что означает, что последний добавленный элемент будет первым, который будет удален. Стеки используются в различных приложениях, таких как управление памятью, выполнение рекурсивных функций и обработка выражений.

## Основные операции со стеком:
- **Push**: Добавление элемента на вершину стека.
- **Pop**: Удаление элемента с вершины стека.
- **Peek (или Top)**: Просмотр элемента на вершине стека без его удаления.
- **IsEmpty**: Проверка, пуст ли стек.
  
## Применение стеков:
- Хранение временных данных, таких как параметры функции и адреса возврата в рекурсивных вызовах.
- Реализация алгоритмов, таких как обход в глубину (DFS) для графов.
- Обработка выражений и арифметических операций.

## Сравнение структур данных: Массивы, Связные списки, Стеки

| Характеристика           | Массивы                         | Связные списки                  | Стеки                          |
|--------------------------|---------------------------------|---------------------------------|--------------------------------|
| **Структура**            | Фиксированная, элементы хранятся в непрерывной области памяти | Динамическая, элементы связаны указателями | Динамическая, элементы добавляются и удаляются только с одной стороны |
| **Доступ к элементам**   | По индексу (O(1))               | Последовательный (O(n))        | По индексу (O(n) для доступа к элементам, O(1) для вершины) |
| **Добавление элемента**   | O(n) (необходима переалокация при увеличении) | O(1) (в начало), O(n) (в конец) | O(1) (на вершину)              |
| **Удаление элемента**     | O(n) (необходима переалокация при уменьшении) | O(1) (из начала), O(n) (из конца) | O(1) (с вершины)              |
| **Память**               | Требуется фиксированное количество памяти | Требуется память для указателей | Требуется память для указателей на вершину |
| **Использование**        | Лучше подходит для статичных наборов данных | Подходит для динамичных наборов данных | Используется для временного хранения данных и реализации алгоритмов |
