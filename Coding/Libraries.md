# Основные библиотеки для Java      

## 1. Коллекции и утилиты

```java
import java.util.ArrayList;
import java.util.HashMap;
import java.util.Collections;
import java.util.stream.Collectors;
```

- **Java Collections Framework (JCF)** — стандартные коллекции (List, Set, Map).
- **Apache Commons Collections** — расширенные коллекции и утилиты.
- **Guava (Google Collections)** — функциональное программирование, работа с коллекциями.

## 2. Работа с JSON и XML

```java
import com.fasterxml.jackson.databind.ObjectMapper;
import org.json.JSONObject;
import javax.xml.parsers.DocumentBuilder;
```

- **Jackson** — работа с JSON.
- **Gson** — альтернативная библиотека для работы с JSON.
- **org.json** — простая обработка JSON.
- **JAXB** — работа с XML.

## 3. Логирование

```java
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
```

- **SLF4J** — универсальный API для логирования.
- **Logback** — продвинутая замена Log4j.
- **Log4j** — классическая библиотека логирования.

## 4. Тестирование

```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;
```

- **JUnit** — стандартное тестирование.
- **TestNG** — альтернатива JUnit с расширенным функционалом.
- **Mockito** — мокирование объектов.
- **AssertJ** — расширенные утверждения.

## 5. HTTP-клиенты

```java
import java.net.http.HttpClient;
import org.apache.http.client.HttpClient;
```

- **Apache HttpClient** — мощный HTTP-клиент.
- **OkHttp** — альтернатива для работы с HTTP.
- **Java HttpClient (JDK 11+)** — стандартный HTTP-клиент.

## 6. Работа с базами данных

```java
import java.sql.Connection;
import org.hibernate.Session;
```

- **JDBC** — стандартный драйвер SQL.
- **Hibernate** — ORM для работы с БД.
- **MyBatis** — альтернатива Hibernate.
- **HikariCP** — пул соединений с БД.

## 7. Работа с многопоточностью

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;
```

- **Java Concurrency API** — стандартные потоки.
- **RxJava** — реактивное программирование.
- **Akka** — акторная модель многопоточности.

## 8. Работа с файлами

```java
import java.nio.file.Files;
import java.io.File;
```

- **Apache Commons IO** — утилиты для работы с файлами.
- **Java NIO** — стандартная работа с файлами.

## 9. Парсинг HTML

```java
import org.jsoup.Jsoup;
```

- **Jsoup** — удобный HTML-парсер.

## 10. Работа с зависимостями

```xml
<dependency>
    <groupId>org.apache.maven</groupId>
    <artifactId>maven-core</artifactId>
    <version>3.8.1</version>
</dependency>
```

- **Maven** — управление зависимостями и сборка проектов.
- **Gradle** — альтернатива Maven, гибкость в настройке сборки.

---

