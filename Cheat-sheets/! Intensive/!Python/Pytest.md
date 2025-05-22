# Шпаргалка по Pytest 🐍📌

## Содержание 🌍 <a id="content"></a>

## [Работа с командной строкой](#cmd)

- [Общая таблица ключей](#cmd-table) — параметры запуска

## [Перезапуск упавших тестов](#rerun)

- [Автоматический `rerun`](#auto-rerun)

## [Параметризация тестов](#parametrize-tests)

- [Как использовать `@pytest.mark.parametrize`](#parametrize-usage)

## [Pytest-xdist - параллелизация](#xdist)

- [Параллельное тестирование](#parallel-tests)

## [Фикстуры](#fixtures)

- [`scope`](#fixture-scope) — область видимости
- [Передача в тест](#passing-fixture)
- [Расположение](#fixture-storage)

## [Маркировки](#markers)

- [Общая таблица маркировок](#marker-table) — декораторы Pytest

## [Декораторы Pytest](#pytest-decorators)

- [Основные декораторы и их применение](#decorators-list)

## [Yield в фикстуре](#yield-fixture)

- [`setup/teardown` через `yield`](#yield-usage)
## [Ассерты в Pytest](#pytest-asserts)

- [Как писать проверки с `assert`](#assert-usage)

---
## Работа с командной строкой <a id="cmd"></a>

### Общая таблица ключей <a id="cmd-table"></a>
В `pytest` есть множество полезных ключей командной строки, которые позволяют управлять запуском тестов и их поведением.

| Ключ                           | Назначение                                                     | Пример команды                       |
| ------------------------------ | -------------------------------------------------------------- | ------------------------------------ |
| `-v`                           | Подробный вывод (verbose)                                      | `pytest -v`                          |
| `-q`                           | Минимальный вывод (quiet)                                      | `pytest -q`                          |
| `-s`                           | Показывает `print()` в консоли                                 | `pytest -s`                          |
| `-k "<substring>"`             | Запуск тестов по подстроке в названии функций                  | `pytest -k "login"`                  |
| `-m "<mark>"`                  | Запуск тестов по маркерам                                      | `pytest -m "smoke"`                  |
| `-x`                           | Остановка после первого неудачного теста                       | `pytest -x`                          |
| `--maxfail=<num>`              | Остановка после `<num>` неудач                                 | `pytest --maxfail=2`                 |
| `--tb=short\|line\|no\|native` | Формат вывода трейсбека                                        | `pytest --tb=short`                  |
| `--lf`                         | Запуск только упавших тестов (last failed)                     | `pytest --lf`                        |
| `--ff`                         | Сначала упавшие, затем остальные (failed first)                | `pytest --ff`                        |
| `--disable-warnings`           | Отключение предупреждений                                      | `pytest --disable-warnings`          |
| `--capture=no`                 | Отключает захват вывода (аналог `-s`)                          | `pytest --capture=no`                |
| `--html=report.html`           | Генерация HTML-отчёта (через `pytest-html`)                    | `pytest --html=report.html`          |
| `--alluredir=path/`            | Сохранение результатов для Allure (папка для данных)           | `pytest --alluredir=allure-results/` |
| `--reuse-db`                   | Повторное использование БД (с `pytest-django`)                 | `pytest --reuse-db`                  |
| `--headless`                   | Режим без GUI (если поддерживается, напр. в браузерных тестах) | `pytest --headless`                  |
| `--cov=project/`               | Покрытие кода (через `pytest-cov`)                             | `pytest --cov=src/`                  |
| `--cov-report=html\|term`      | Отчёт покрытия (html, терминал)                                | `pytest --cov-report=html`           |
[🔼 К содержанию](#content)

---
## Перезапуск упавших тестов <a id="rerun"></a>
### Автоматический перезапуск упавших тестов <a id="rerun-auto"></a>

Для повторного запуска упавших тестов используется плагин [`pytest-rerunfailures`](https://pypi.org/project/pytest-rerunfailures/).

Для `pytest` есть плагин [`pytest-rerunfailures`](https://pypi.org/project/pytest-rerunfailures/), который добавляет опции для автоматического повторного запуска упавших тестов.

#### Установка
```bash
pip install pytest-rerunfailures
```

**Основные опции**

| Ключ                  | Назначение                            | Пример команды                     |
|-----------------------|-------------------------------------|------------------------------------|
| --reruns <N>          | Перезапускать упавшие тесты N раз   | pytest --reruns 3                  |
| --reruns-delay <сек>  | Задержка между перезапусками в сек. | pytest --reruns 3 --reruns-delay 2 |

**Пример настройки на уровне теста**

Можно указать количество перезапусков и задержку в декораторе @pytest.mark.flaky для отдельного теста:

```python
import pytest
import random

@pytest.mark.flaky(reruns=2, reruns_delay=1)
def test_unstable():
    assert random.randint(0, 1)
```

[🔼 К содержанию](#content)

---
## Параметризация тестов  <a id="parametrize-tests"></a>
### Как использовать `@pytest.mark.parametrize` <a id="parametrize-usage"></a>

Параметризация в pytest позволяет запускать один тест с разными наборами входных данных, что упрощает проверку множества вариантов без дублирования кода.

#### Синтаксис

@pytest.mark.parametrize("параметры", [список_значений])

#### Пример
```python
@pytest.mark.parametrize("input,expected", [
    (2, 4),
    (3, 9),
    (4, 16),
])
def test_square(input, expected):
    assert input ** 2 == expected
```
Тест `test_square` будет выполнен три раза с разными параметрами.

[🔼 К содержанию](#content)
 
---
## Pytest-xdist - параллелизация <a id="xdist"></a>

### Параллельное тестирование <a id="parallel-tests"></a>

Для ускорения прогона большого количества тестов можно запускать их параллельно с помощью плагина `pytest-xdist`.

#### Что такое xdist?

`pytest-xdist` — это расширение для `pytest`, позволяющее распределённо или параллельно запускать тесты, что особенно полезно в больших проектах и CI/CD.

#### Установка
```python
pip install pytest-xdist
```
#### Основные опции

| Ключ           | Назначение                                 | Пример команды             |
|----------------|--------------------------------------------|----------------------------|
| -n <num>       | Количество параллельных потоков (воркеров) | pytest -n 4                |
| --dist=loadscope | Распределение по scope (модули, классы)   | pytest -n 4 --dist=loadscope |
| --maxfail=<N>  | Прервать после N неудач                    | pytest -n 4 --maxfail=2    |

#### Пример
```python
pytest -n 4
```
Эта команда запустит тесты в 4 потоках одновременно, автоматически распределяя их между воркерами.

[🔼 К содержанию](#content)

---

## Фикстуры  <a id="fixtures "></a>

### Область видимости фикстур (`scope`) <a id="fixture-scope"></a>

Параметр `scope` определяет, как долго будет "жить" фикстура — то есть, как часто она будет создаваться и уничтожаться.

Доступные значения:

- function — по умолчанию; фикстура создаётся заново для каждого теста.
- class — фикстура создаётся один раз для каждого класса тестов.
- module — фикстура создаётся один раз для каждого модуля.
- package — фикстура создаётся один раз на пакет (с Python 3.9+).
- session — фикстура создаётся один раз за всю сессию pytest.

Пример:
```python
import pytest

@pytest.fixture(scope="module")
def db_connection():
    print("Установка соединения с БД")
    yield
    print("Отключение от БД")
```
### Передача фикстур в тест <a id="passing-fixture"></a>

Фикстура передаётся в тест как аргумент функции. Pytest сам подставит нужное значение по имени.

Пример:
```python
@pytest.fixture
def user():
    return {"id": 1, "name": "Alice"}

def test_user_name(user):
    assert user["name"] == "Alice"
```
### Расположение фикстур <a id="fixture-storage"></a>

Фикстуры можно определять:

- прямо в файле с тестами — локально
- в отдельном файле `conftest.py` — глобально для всей директории
- в общем тестовом пакете с указанием `pytest_plugins` — для переиспользования в разных проектах

[🔼 К содержанию](#content)

---

## Маркировки  <a id="markers"></a>

### Общая таблица маркировок— декораторы Pytest <a id="marker-table"></a>

Pytest предоставляет встроенные маркеры, а также позволяет определять собственные. Ниже приведены основные **встроенные** маркеры, доступные в Pytest "из коробки":

| Маркер            | Назначение                                                                 |
|-------------------|----------------------------------------------------------------------------|
| skip              | Безусловно пропустить выполнение теста                                     |
| skipif            | Пропустить тест при выполнении указанного условия                         |
| xfail             | Отметить тест как ожидаемо падающий (Expected Failure)                     |
| parametrize       | Параметризация тестов                                                      |
| usefixtures       | Указать фикстуры, которые будут использоваться явно                        |
| filterwarnings    | Обработка предупреждений внутри теста                                      |
| mark.parametrize  | Альтернативный синтаксис параметризации (то же, что и parametrize)         |
| mark.usefixtures  | Альтернативный способ явно применить фикстуру                              |
| mark.tryfirst     | Указать, что тест должен выполняться раньше других                         |
| mark.trylast      | Указать, что тест должен выполняться позже других                          |
| mark.run(order=N) | (требует `pytest-order`) Явный порядок запуска тестов                      |
| mark.flaky        | (с `pytest-rerunfailures`) для перезапуска нестабильных тестов             |
| mark.asyncio      | (с `pytest-asyncio`) для тестов с async/await                              |
| mark.django_db    | (с `pytest-django`) доступ к базе данных Django                            |
| mark.parametrize_file | (с `pytest-cases`, `pytest-datafiles`) параметризация из файла         |
Примеры использования:
```python
@pytest.mark.skip(reason="Тест временно отключён")
```

```python
@pytest.mark.skipif(sys.platform == "win32", reason="Не работает на Windows")
```

```python
@pytest.mark.xfail(reason="Баг #123")
```

```python
@pytest.mark.parametrize("x, y", [(1, 2), (3, 4)])
```

Вы можете создавать свои собственные маркеры (например, `@pytest.mark.smoke`, `@pytest.mark.api`, `@pytest.mark.regression`) и регистрировать их в `pytest.ini`, чтобы избежать предупреждений:

```python
[pytest]
markers =
    smoke: Быстрые проверки основного функционала
    api: Тесты для API
    regression: Регрессионные тесты
    slow: Медленные тесты
    integration: Интеграционные тесты
```

[🔼 К содержанию](#content)

---

## Декораторы Pytest  <a id="pytest-decorators"></a>

### Основные декораторы и их применение  <a id="decorators-list"></a>

Вот список **основных декораторов**, применяемых в тестировании:

| Декоратор                   | Назначение                                                       | Пример                                     |
|-----------------------------|------------------------------------------------------------------|--------------------------------------------|
| @pytest.mark.skip           | Пропустить тест                                                  | @pytest.mark.skip(reason="временно")       |
| @pytest.mark.skipif         | Пропустить при условии                                           | @pytest.mark.skipif(cond, reason="...")    |
| @pytest.mark.xfail          | Отметить тест как ожидаемо падающий                              | @pytest.mark.xfail(reason="баг #123")      |
| @pytest.mark.parametrize    | Параметризация теста                                             | @pytest.mark.parametrize(...)              |
| @pytest.mark.usefixtures    | Применить фикстуру явно (без передачи в аргументы)               | @pytest.mark.usefixtures("setup")          |
| @pytest.mark.flaky          | Повторный запуск при падении (с плагином `pytest-rerunfailures`) | @pytest.mark.flaky(reruns=2, reruns_delay=1) |
| @pytest.fixture             | Определение фикстуры                                             | @pytest.fixture(scope="module")            |
| @pytest.mark.asyncio        | Поддержка async-тестов (с `pytest-asyncio`)                      | @pytest.mark.asyncio                       |

Эти декораторы позволяют гибко управлять выполнением тестов и их конфигурацией.

[🔼 К содержанию](#content)

---

## Yield в фикстуре <a id="yield-fixture"></a>

### `setup/teardown` через `yield`  <a id="yield-usage"></a>

В фикстурах pytest можно использовать `yield` вместо `return`, чтобы определить поведение **до** и **после** выполнения теста — это удобно для реализации `setup` и `teardown` в одном месте.

#### Принцип работы

- Все, что написано **до** `yield`, считается **подготовкой окружения** (setup).
- Все, что написано **после** `yield`, выполняется **после теста** (teardown), даже если тест упал.

#### Пример
```python
import pytest

@pytest.fixture
def connect_db():
    print("Подключение к БД")
    yield "db_connection"
    print("Отключение от БД")

def test_query(connect_db):
    assert connect_db == "db_connection"
```

В этом примере:
- Перед выполнением теста произойдёт подключение к БД.
- После выполнения — отключение, независимо от результата.

[🔼 К содержанию](#content)

---

## Ассерты в Pytest <a id="pytest-asserts"></a>

 ### Как писать проверки с `assert`  <a id="assert-usage"></a>

В pytest используются стандартные Python-выражения `assert` для проверки условий внутри тестов. Это удобно и читаемо, а также даёт подробные сообщения об ошибках без дополнительного кода.

#### Синтаксис
```python
assert условие, "сообщение об ошибке (опционально)"
```
#### Примеры использования
```python
assert 2 + 2 == 4
```
```python
assert user["name"] == "Alice", "Имя пользователя должно быть Alice"
```
```python
assert response.status_code == 200
```
#### Поведение при падении

Если `assert` не проходит — тест считается упавшим.  
Pytest автоматически анализирует выражение и выводит подробности, например:
```python
assert user["name"] == "Alice"
```
E   AssertionError: assert 'Bob' == 'Alice'  
E     - Alice  
E     + Bob

Благодаря этому не нужно вручную писать сообщения об ошибке — достаточно использовать `assert`.

[🔼 К содержанию](#content)

---