# Деревья

**Дерево** — это нелинейная структура данных, состоящая из узлов (вершин), каждый из которых содержит данные и ссылки на дочерние узлы. Деревья часто используются для представления иерархий, организации данных в поисковых структурах, компиляторов и файловых систем.

## Основные типы деревьев:
1. **Двоичные деревья**  
2. **AVL-деревья**  
3. **B-деревья**  

### 1. Двоичные деревья

Двоичное дерево — это дерево, в котором каждый узел имеет не более двух дочерних узлов: **левый** и **правый**.

**Особенности двоичных деревьев:**
- Каждый узел имеет до двух дочерних узлов.
- Левый потомок содержит значение меньше или равно значению родителя, а правый потомок — большее.
  
**Основные операции на двоичном дереве:**
- **Поиск**: O(log n) в сбалансированном дереве, O(n) в несбалансированном.
- **Вставка**: Добавление элемента на соответствующее место в соответствии с его значением.
- **Удаление**: Удаление узла с последующей перестройкой дерева.

**Виды обхода двоичных деревьев:**
- **In-order** (Левый, Корень, Правый): Используется для получения отсортированных данных.
- **Pre-order** (Корень, Левый, Правый): Полезен для создания копии дерева.
- **Post-order** (Левый, Правый, Корень): Применяется для удаления дерева.

### 2. AVL-деревья

**AVL-дерево** — это самобалансирующееся двоичное дерево поиска, в котором разница высот двух поддеревьев каждого узла всегда равна 1 или меньше. Это гарантирует, что высота дерева остается O(log n), что улучшает время выполнения операций поиска, вставки и удаления по сравнению с несбалансированными деревьями.

**Особенности AVL-деревьев:**
- Балансировка осуществляется автоматически при вставке или удалении узлов с помощью вращений (левое, правое, левое-правое, правое-левое вращения).
- Разница высот двух поддеревьев для любого узла — не более 1.

**Основные операции на AVL-дереве:**
- **Поиск**: O(log n)
- **Вставка**: O(log n), с последующей балансировкой.
- **Удаление**: O(log n), также с возможной балансировкой.

### 3. B-деревья

**B-дерево** — это самобалансирующееся дерево поиска, предназначенное для работы с большими объемами данных, которые не помещаются в оперативной памяти. Оно обеспечивает эффективные операции поиска, вставки и удаления, даже если данные хранятся на внешних носителях (диск, база данных).

**Особенности B-деревьев:**
- В каждом узле может быть несколько ключей.
- В отличие от двоичных деревьев, каждый узел B-дерева может иметь более двух потомков.
- Используются в файловых системах и базах данных для минимизации количества операций ввода-вывода.

**Свойства B-деревьев:**
- Все листья находятся на одном уровне.
- Узлы могут содержать от `t-1` до `2t-1` ключей, где `t` — минимальный порядок дерева.
- B-дерево минимизирует количество операций ввода-вывода при доступе к данным.

**Основные операции на B-дереве:**
- **Поиск**: O(log n)
- **Вставка**: O(log n) с возможным разбиением узлов.
- **Удаление**: O(log n) с возможным объединением узлов.

## Сравнение типов деревьев

| Характеристика         | Двоичные деревья             | AVL-деревья                 | B-деревья                   |
|------------------------|------------------------------|-----------------------------|-----------------------------|
| **Количество потомков** | До 2                         | До 2                        | От `t` до `2t` потомков     |
| **Сбалансированность**  | Может быть несбалансированным | Всегда сбалансировано       | Сбалансировано              |
| **Операции поиска**     | O(log n) — в сбалансированном дереве | O(log n)                    | O(log n)                    |
| **Балансировка**        | Не осуществляется            | Происходит при необходимости| Происходит при необходимости|
| **Применение**          | Поиск, сортировка данных     | Поиск, где важно время ответа| Поиск в базах данных, файловых системах |