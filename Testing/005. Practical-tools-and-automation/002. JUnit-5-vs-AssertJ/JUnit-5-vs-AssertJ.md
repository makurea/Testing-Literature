# JUnit 5 и AssertJ (параметризация тестов)

## JUnit 5

**JUnit 5** — это современная библиотека для написания и выполнения тестов в языке программирования Java. JUnit 5 является частью семейства JUnit и состоит из трех основных модулей:

1. **JUnit Platform**: Поддерживает запуск тестов на различных средах выполнения тестов, включая JUnit 3 и JUnit 4. Он предоставляет основу для запуска тестов и интеграции с различными инструментами и средами.

2. **JUnit Jupiter**: Является основной библиотекой для написания тестов и расширений в JUnit 5. Он включает в себя новые аннотации и API для создания тестов.

3. **JUnit Vintage**: Обеспечивает совместимость с тестами, написанными для JUnit 3 и JUnit 4, что позволяет запускать старые тесты в рамках JUnit 5.

### Основные особенности JUnit 5

- **Аннотации**: JUnit 5 вводит новые аннотации, такие как `@Test`, `@BeforeEach`, `@AfterEach`, `@BeforeAll`, `@AfterAll`, и `@Nested`, которые упрощают написание и организацию тестов.
- **Параметризация тестов**: JUnit 5 поддерживает параметризацию тестов через аннотацию `@ParameterizedTest`, что позволяет запускать один и тот же тест с разными входными данными.
- **Расширяемость**: JUnit 5 предоставляет механизм расширений, который позволяет создавать собственные расширения и интегрировать сторонние библиотеки.
- **Динамическое тестирование**: JUnit 5 поддерживает динамическое тестирование через аннотацию `@TestFactory`, что позволяет создавать тесты во время выполнения.

## AssertJ

**AssertJ** — это библиотека для утверждений (assertions) в Java, которая предоставляет мощный и удобный API для написания проверок в тестах. AssertJ обеспечивает читаемость и выразительность проверок и поддерживает богатый набор методов для проверки различных типов данных.

### Основные особенности AssertJ

- **Читаемость**: AssertJ предоставляет fluent API, который позволяет писать утверждения, которые легко читаемы и понятны.
- **Поддержка различных типов данных**: AssertJ поддерживает проверки для строк, коллекций, чисел, дат, и других типов данных.
- **Дополнительные проверки**: AssertJ предоставляет множество дополнительных проверок, таких как проверка содержимого коллекций, состояния объектов и других аспектов.
- **Интеграция с JUnit**: AssertJ можно легко интегрировать с JUnit, позволяя использовать его вместе с JUnit 5 для создания выразительных и мощных тестов.

## Параметризация тестов в JUnit 5

**Параметризация тестов** позволяет запускать один и тот же тест с различными входными данными. Это полезно для проверки различных сценариев и данных без необходимости писать отдельные тесты для каждого случая.

### Аннотации для параметризации тестов в JUnit 5

- `@ParameterizedTest` — аннотация, используемая для обозначения метода теста, который будет запускаться с разными входными данными.
- `@ValueSource` — предоставляет одно или несколько значений для параметра теста.
- `@EnumSource` — предоставляет значения из перечисления (enum) для параметра теста.
- `@CsvSource` — предоставляет данные в формате CSV (Comma-Separated Values) для параметра теста.
- `@MethodSource` — указывает метод, который возвращает поток данных для параметризации теста.
- `@ArgumentsSource` — позволяет использовать пользовательский источник аргументов для параметризации тестов.

## Примеры применения

- **Тестирование с разными входными данными**: Использование параметризации для выполнения одного и того же теста с различными значениями входных данных.
- **Проверка различных сценариев**: Использование параметризации для проверки разных сценариев, таких как обработка разных типов данных или проверка граничных значений.
- **Упрощение тестов**: Сокращение количества тестовых методов и упрощение тестов за счёт использования одного метода для проверки нескольких случаев.

JUnit 5 и AssertJ вместе обеспечивают мощный и гибкий инструмент для написания тестов в Java, позволяя создавать выразительные и легко поддерживаемые тесты с помощью параметризации и удобного API для проверок.