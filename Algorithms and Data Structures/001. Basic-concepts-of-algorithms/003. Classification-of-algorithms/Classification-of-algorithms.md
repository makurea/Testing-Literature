# Классификация алгоритмов

Алгоритмы можно классифицировать по различным критериям, основываясь на их логической структуре, области применения и способах решения задач. Вот основные категории:

### 1. По способу выполнения:
   - **Детерминированные алгоритмы**  
     Алгоритмы, которые всегда выполняют одно и то же действие при одинаковых входных данных, обеспечивая предсказуемый результат.

   - **Недетерминированные алгоритмы**  
     Алгоритмы, в которых на некоторых шагах может происходить выбор нескольких вариантов выполнения. В зависимости от выбора, результат может варьироваться.

   - **Стохастические алгоритмы**  
     Алгоритмы, использующие случайные величины или приближенные значения для достижения результата.

### 2. По методам решения задач:
   - **Жадные алгоритмы (Greedy algorithms)**  
     Выбирают на каждом шаге локально оптимальное решение, надеясь, что оно приведет к глобально оптимальному результату.

   - **Алгоритмы "Разделяй и властвуй" (Divide and Conquer)**  
     Задача разбивается на подзадачи, каждая из которых решается рекурсивно. Примеры – быстрая сортировка, сортировка слиянием.

   - **Динамическое программирование (Dynamic Programming)**  
     Решает сложные задачи путем разбиения их на более простые подзадачи, результаты которых запоминаются для предотвращения повторных вычислений.

   - **Жадный поиск с возвратом (Backtracking)**  
     Поиск возможных решений задачи путем рекурсивного перебора с возвратом при обнаружении тупиков.

   - **Алгоритмы полного перебора (Brute Force)**  
     Полный перебор всех возможных решений для нахождения оптимального.

   - **Эвристические алгоритмы**  
     Алгоритмы, которые не гарантируют нахождение оптимального решения, но предоставляют приемлемые результаты за разумное время.

### 3. По структуре данных:
   - **Алгоритмы на массивах**  
     Оперируют последовательностями данных фиксированного размера. Примеры – сортировка пузырьком, быстрая сортировка.

   - **Алгоритмы на деревьях**  
     Работают с древовидными структурами данных. Примеры – обход дерева, бинарное дерево поиска.

   - **Алгоритмы на графах**  
     Оперируют вершинами и ребрами графа. Примеры – алгоритм Дейкстры, поиск в ширину (BFS) и в глубину (DFS).

   - **Алгоритмы на строках**  
     Оперируют строками символов. Примеры – алгоритм Кнута-Морриса-Пратта для поиска подстроки.

### 4. По типу задачи:
   - **Сортировка**  
     Алгоритмы, упорядочивающие элементы набора данных по определённому критерию. Примеры – быстрая сортировка, сортировка слиянием.

   - **Поиск**  
     Алгоритмы для нахождения элемента или множества элементов в структуре данных. Примеры – бинарный поиск, линейный поиск.

   - **Комбинаторные алгоритмы**  
     Решают задачи, связанные с генерацией и выбором комбинаций, перестановок или подмножеств. Пример – задача о рюкзаке.

   - **Графовые алгоритмы**  
     Оперируют вершинами и рёбрами для решения задач на графах. Примеры – поиск кратчайшего пути, нахождение минимального остовного дерева.

### 5. По парадигме выполнения:
   - **Итеративные алгоритмы**  
     Выполняют задачу с использованием циклов (for, while), повторяя шаги до достижения результата.

   - **Рекурсивные алгоритмы**  
     Решают задачу, вызывая самих себя для решения подзадач.

   - **Параллельные и многопоточные алгоритмы**  
     Разбивают задачу на несколько частей, которые выполняются одновременно в разных потоках или процессах.

### 6. По времени выполнения:
   - **Онлайн-алгоритмы**  
     Могут принимать и обрабатывать входные данные последовательно по мере их поступления.

   - **Офлайн-алгоритмы**  
     Получают все данные для обработки сразу и решают задачу, имея полный набор информации.

### 7. По области применения:
   - **Криптографические алгоритмы**  
     Используются для шифрования и защиты данных. Примеры – RSA, AES.

   - **Алгоритмы машинного обучения**  
     Оперируют с большими наборами данных для обучения моделей. Примеры – градиентный спуск, алгоритм k-ближайших соседей.

   - **Сетевые алгоритмы**  
     Оперируют с передачей данных по сетям. Примеры – алгоритм маршрутизации Дейкстры, алгоритм окон TCP.

Алгоритмы являются основой программирования и решают широкий круг задач. Правильная классификация позволяет эффективно выбрать алгоритм для конкретной задачи и оптимизировать его производительность.