# Шпаргалка по SQL с примерами использования

| **Категория**                    | **Ключевое слово** | **Описание**                                                                                                    | **Пример**                             |
|----------------------------------|---------------------|----------------------------------------------------------------------------------------------------------------|----------------------------------------|
| **Объединение и агрегация данных** | `JOIN`            | Объединяет строки из двух таблиц на основе общего столбца.                                                     | `SELECT * FROM A JOIN B ON A.id = B.id;` |
|                                  | `INNER JOIN`       | Возвращает только строки с совпадениями в обеих таблицах.                                                      | `SELECT * FROM A INNER JOIN B ON A.id = B.id;` |
|                                  | `LEFT JOIN`        | Возвращает все строки из левой таблицы и соответствующие строки из правой.                                     | `SELECT * FROM A LEFT JOIN B ON A.id = B.id;` |
|                                  | `RIGHT JOIN`       | Возвращает все строки из правой таблицы и соответствующие строки из левой.                                     | `SELECT * FROM A RIGHT JOIN B ON A.id = B.id;` |
|                                  | `FULL OUTER JOIN`  | Возвращает все строки из обеих таблиц, включая строки без совпадений.                                          | `SELECT * FROM A FULL OUTER JOIN B ON A.id = B.id;` |
|                                  | `GROUP BY`         | Группирует результаты по одному или нескольким столбцам.                                                       | `SELECT dept, COUNT(*) FROM employees GROUP BY dept;` |
|                                  | `HAVING`           | Фильтрует группы, созданные с помощью GROUP BY.                                                                | `SELECT dept, COUNT(*) FROM employees GROUP BY dept HAVING COUNT(*) > 5;` |
|                                  | `COUNT`            | Подсчитывает количество строк или непустых значений.                                                           | `SELECT COUNT(*) FROM employees;` |
|                                  | `SUM`              | Вычисляет сумму числовых значений в группе.                                                                    | `SELECT SUM(salary) FROM employees;` |
|                                  | `AVG`              | Вычисляет среднее значение числовых значений в группе.                                                         | `SELECT AVG(salary) FROM employees;` |
|                                  | `MIN`              | Находит минимальное значение в группе.                                                                         | `SELECT MIN(salary) FROM employees;` |
|                                  | `MAX`              | Находит максимальное значение в группе.                                                                        | `SELECT MAX(salary) FROM employees;` |

| **Фильтрация данных**            | **Ключевое слово** | **Описание**                                                                                                    | **Пример**                             |
|----------------------------------|---------------------|----------------------------------------------------------------------------------------------------------------|----------------------------------------|
| **Фильтрация**                   | `WHERE`            | Фильтрует строки на основе условия.                                                                            | `SELECT * FROM employees WHERE age > 30;` |
|                                  | `BETWEEN`          | Проверяет, находится ли значение в указанном диапазоне.                                                        | `SELECT * FROM employees WHERE age BETWEEN 25 AND 35;` |
|                                  | `IN`               | Проверяет, содержится ли значение в списке.                                                                    | `SELECT * FROM employees WHERE dept IN ('IT', 'Sales');` |
|                                  | `LIKE`             | Ищет строки по шаблону.                                                                                        | `SELECT * FROM employees WHERE name LIKE 'A%';` |
|                                  | `IS NULL`          | Проверяет, является ли значение NULL.                                                                          | `SELECT * FROM employees WHERE manager_id IS NULL;` |
|                                  | `IS NOT NULL`      | Проверяет, не является ли значение NULL.                                                                       | `SELECT * FROM employees WHERE manager_id IS NOT NULL;` |
|                                  | `EXISTS`           | Проверяет, возвращает ли подзапрос строки.                                                                     | `SELECT * FROM employees WHERE EXISTS (SELECT 1 FROM dept WHERE dept.id = employees.dept_id);` |

| **Функции для работы с данными** | **Ключевое слово** | **Описание**                                                                                                    | **Пример**                             |
|----------------------------------|---------------------|----------------------------------------------------------------------------------------------------------------|----------------------------------------|
| **Условные функции**             | `COALESCE`         | Возвращает первое не-NULL значение из списка выражений.                                                        | `SELECT COALESCE(manager_id, 0) FROM employees;` |
|                                  | `NULLIF`           | Возвращает NULL, если два выражения равны; иначе возвращает первое.                                            | `SELECT NULLIF(salary, 0) FROM employees;` |
|                                  | `CASE WHEN`        | Создает условные выражения.                                                                                    | `SELECT CASE WHEN salary > 5000 THEN 'High' ELSE 'Low' END FROM employees;` |
|                                  | `CAST`             | Преобразует данные к указанному типу.                                                                          | `SELECT CAST(salary AS FLOAT) FROM employees;` |
|                                  | `CONVERT`          | Преобразует выражение к заданному типу данных.                                                                 | `SELECT CONVERT(VARCHAR, salary) FROM employees;` |

| **Модификация данных**           | **Ключевое слово** | **Описание**                                                                                                    | **Пример**                             |
|----------------------------------|---------------------|----------------------------------------------------------------------------------------------------------------|----------------------------------------|
| **Операции с данными (CRUD)**    | `INSERT`           | Добавляет новые строки в таблицу.                                                                              | `INSERT INTO employees (name, dept) VALUES ('Alice', 'HR');` |
|                                  | `UPDATE`           | Обновляет существующие строки в таблице.                                                                       | `UPDATE employees SET salary = 6000 WHERE id = 1;` |
|                                  | `DELETE`           | Удаляет строки из таблицы.                                                                                     | `DELETE FROM employees WHERE id = 1;` |
|                                  | `MERGE`            | Объединяет операции `INSERT`, `UPDATE` и `DELETE` на основе условий.                                           | `MERGE INTO employees AS target USING new_employees AS source ON target.id = source.id ...` |

| **Разное**                       | **Ключевое слово** | **Описание**                                                                                                    | **Пример**                             |
|----------------------------------|---------------------|----------------------------------------------------------------------------------------------------------------|----------------------------------------|
| **Другие команды**               | `DISTINCT`         | Удаляет дубликаты из результата запроса.                                                                       | `SELECT DISTINCT dept FROM employees;` |
|                                  | `ORDER BY`         | Сортирует результаты запроса по указанным столбцам.                                                            | `SELECT * FROM employees ORDER BY salary DESC;` |
|                                  | `LIMIT`            | Ограничивает количество возвращаемых строк.                                                                    | `SELECT * FROM employees LIMIT 10;` |
|                                  | `OFFSET`           | Пропускает указанное количество строк перед началом возврата результатов.                                      | `SELECT * FROM employees OFFSET 5;` |
|                                  | `UNION`            | Объединяет результаты двух или более SELECT операторов, удаляя дубликаты.                                      | `SELECT name FROM A UNION SELECT name FROM B;` |
|                                  | `UNION ALL`        | Объединяет результаты двух или более SELECT операторов, включая дубликаты.                                     | `SELECT name FROM A UNION ALL SELECT name FROM B;` |
|                                  | `WITH`             | Определяет общее табличное выражение (CTE) для подзапросов.                                                   | `WITH DeptAvg AS (SELECT dept, AVG(salary) AS avg_salary FROM employees GROUP BY dept) SELECT * FROM DeptAvg;` |
|                                  | `EXPLAIN`          | Показывает план выполнения запроса, полезно для оптимизации.                                                   | `EXPLAIN SELECT * FROM employees WHERE age > 30;` |
|                                  | `INDEX`            | Создает индекс для ускорения запросов.                                                                         | `CREATE INDEX idx_salary ON employees (salary);` |
|                                  | `VIEW`             | Создает виртуальную таблицу на основе запроса.                                                                 | `CREATE VIEW high_salaries AS SELECT * FROM employees WHERE salary > 5000;` |
|                                  | `TRIGGER`          | Настраивает автоматические действия, выполняемые при определенных событиях базы данных.                        | `CREATE TRIGGER before_insert BEFORE INSERT ON employees FOR EACH ROW BEGIN ... END;` |
|                                  | `TRANSACTION`      | Управляет последовательностью операций как единой транзакцией.                                                 | `BEGIN TRANSACTION; ... COMMIT;` |
|                                  | `ROLLBACK`         | Отменяет транзакцию до сохраненной точки или начала.                                                           | `ROLLBACK;` |
|                                  | `COMMIT`           | Сохраняет изменения, сделанные в транзакции.                                                                   | `COMMIT;` |
|                                  | `SAVEPOINT`        | Создает точку внутри транзакции, к которой можно откатиться.                                                   | `SAVEPOINT sp1;` |
