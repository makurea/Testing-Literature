# Шпаргалка по библиотекам Java

| Название библиотеки | Что делает | Пример кода |
|---------------------|------------|-------------|
| **Apache Commons Lang** | Предоставляет дополнительные утилиты для работы со строками, числами, датами и другими объектами. | ```java
import org.apache.commons.lang3.StringUtils;

public class Example {
    public static void main(String[] args) {
        String str = "  Hello World  ";
        String trimmed = StringUtils.trim(str); // "Hello World"
    }
}
``` |
| **Google Guava** | Библиотека от Google, предоставляющая множество полезных утилит для работы с коллекциями, строками, вводом-выводом и многопоточностью. | ```java
import com.google.common.base.Joiner;
import java.util.Arrays;

public class Example {
    public static void main(String[] args) {
        String result = Joiner.on(", ").join(Arrays.asList("apple", "banana", "cherry")); // "apple, banana, cherry"
    }
}
``` |
| **Jackson** | Библиотека для работы с JSON, позволяет сериализовать и десериализовать объекты Java в JSON и обратно. | ```java
import com.fasterxml.jackson.databind.ObjectMapper;

public class Example {
    public static void main(String[] args) throws Exception {
        ObjectMapper mapper = new ObjectMapper();
        Person person = new Person("John", "Doe");
        String json = mapper.writeValueAsString(person); // {"firstName":"John","lastName":"Doe"}
    }
}

class Person {
    public String firstName;
    public String lastName;

    public Person(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }
}
``` |
| **Lombok** | Библиотека для упрощения кода, автоматически генерирует геттеры, сеттеры, конструкторы и другие повторяющиеся методы. | ```java
import lombok.Data;

@Data
public class Person {
    private String firstName;
    private String lastName;
}
``` |
| **JUnit** | Фреймворк для модульного тестирования, позволяет писать и запускать тесты для проверки корректности кода. | ```java
import org.junit.Test;
import static org.junit.Assert.*;

public class ExampleTest {
    @Test
    public void testAddition() {
        Calculator calculator = new Calculator();
        assertEquals(5, calculator.add(2, 3));
    }
}

class Calculator {
    public int add(int a, int b) {
        return a + b;
    }
}
``` |
| **Mockito** | Библиотека для создания мок-объектов, позволяет имитировать поведение объектов в тестах. | ```java
import org.junit.Test;
import static org.mockito.Mockito.*;

public class ExampleTest {
    @Test
    public void testMock() {
        Person person = mock(Person.class);
        when(person.getName()).thenReturn("John Doe");
        assertEquals("John Doe", person.getName());
    }
}

class Person {
    public String getName() {
        return "Real Name";
    }
}
``` |
| **Spring Framework** | Фреймворк для создания корпоративных приложений, предоставляет множество инструментов для работы с зависимостями, веб-разработкой и многопоточностью. | ```java
import org.springframework.context.ApplicationContext;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;

public class Example {
    public static void main(String[] args) {
        ApplicationContext context = new AnnotationConfigApplicationContext(AppConfig.class);
        MyBean myBean = context.getBean(MyBean.class);
        myBean.doSomething();
    }
}

class MyBean {
    public void doSomething() {
        System.out.println("Doing something");
    }
}

class AppConfig {
    @Bean
    public MyBean myBean() {
        return new MyBean();
    }
}
``` |