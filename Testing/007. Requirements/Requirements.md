# Требования и их атрибуты

Требования — это описание того, как должна функционировать система, включая её поведение, характеристики, ограничения и другие аспекты, которые необходимы для удовлетворения потребностей пользователей и бизнеса. Правильная постановка требований — один из ключевых факторов успеха проекта, так как они определяют, что именно должно быть разработано и протестировано.

## Виды требований

### 1. **Функциональные требования**
Функциональные требования описывают, что система должна делать. Они определяют конкретные функции, действия и возможности, которые программное обеспечение должно обеспечивать.

Примеры:
- Система должна позволять пользователю создавать учетную запись.
- Программа должна отправлять уведомления о новых сообщениях.
- Пользователь может восстановить забытый пароль через email.

### 2. **Нефункциональные требования**
Нефункциональные требования описывают аспекты системы, которые не связаны с конкретными функциями, но важны для её качества и производительности. Это могут быть требования к производительности, безопасности, удобству использования, совместимости и другим характеристикам.

Примеры:
- Система должна обрабатывать не менее 1000 запросов в секунду.
- Время отклика на запрос не должно превышать 2 секунд.
- Данные пользователя должны быть зашифрованы в базе данных.

### 3. **Бизнес-требования**
Бизнес-требования определяют цели и задачи, которые должна достичь система с точки зрения бизнеса. Они описывают, почему система разрабатывается и как она должна помогать бизнесу.

Примеры:
- Увеличение количества пользователей на 15% в течение первого года.
- Снижение операционных затрат на 10% после внедрения новой системы.

### 4. **Системные требования**
Системные требования описывают технические аспекты и инфраструктуру, необходимые для работы системы, включая оборудование, программное обеспечение и сети.

Примеры:
- Приложение должно работать на всех версиях операционной системы Windows от версии 10 и выше.
- Серверная часть системы должна поддерживать базы данных MySQL и PostgreSQL.

## Атрибуты требований

Для того чтобы требования были полными, понятными и управляемыми, они должны обладать определёнными атрибутами.

### 1. **Однозначность (Unambiguous)**
Требования должны быть сформулированы так, чтобы их можно было трактовать только одним способом. Избегайте двусмысленности и использования неопределённых терминов.

**Пример:** Плохое требование: "Программа должна быстро обрабатывать данные".  
Хорошее требование: "Время обработки данных не должно превышать 2 секунд при 1000 запросах в минуту".

### 2. **Полнота (Complete)**
Требования должны быть полными, т.е. описывать все аспекты поведения системы и не оставлять неясностей.

**Пример:** Требование должно охватывать все функциональные и нефункциональные аспекты, необходимые для работы системы, включая ошибки, которые могут возникнуть.

### 3. **Проверяемость (Verifiable)**
Требования должны быть проверяемыми. Это значит, что по каждому требованию можно разработать тесты для подтверждения его выполнения.

**Пример:** Требование "Система должна быть удобной в использовании" непроверяемо. Требование "Среднее время выполнения операции по созданию учетной записи не должно превышать 1 минуты" проверяемо.

### 4. **Необходимость (Necessary)**
Требования должны быть действительно необходимыми для достижения целей системы и выполнения её задач.

**Пример:** Избегайте включения в проект требований, которые не добавляют ценности или не являются критичными для пользователя.

### 5. **Консистентность (Consistent)**
Требования не должны противоречить друг другу или другим частям проектной документации.

**Пример:** Если одно требование указывает, что система должна поддерживать одновременную работу 100 пользователей, другое требование не может ограничивать эту цифру, например, до 50.

### 6. **Приоритизация (Prioritized)**
Требования должны быть классифицированы по приоритету, чтобы команда разработки могла сосредоточиться на наиболее важных функциях в первую очередь.

**Пример:** Использование категорий приоритета: критичные, высокие, средние, низкие.

### 7. **Атомарность (Atomic)**
Каждое требование должно быть разбито на отдельные, неделимые части. Это упрощает их реализацию и тестирование.

**Пример:** Плохое требование: "Система должна позволять пользователю создавать учетные записи и отправлять уведомления".  
Хорошее требование: 1. Система должна позволять пользователю создавать учетные записи. 2. Система должна отправлять уведомления.

### 8. **Трассируемость (Traceable)**
Для каждого требования должно быть возможно проследить его происхождение (источник), а также его связь с другими артефактами разработки, такими как тест-кейсы или код.

**Пример:** Каждое требование должно иметь уникальный идентификатор, чтобы его можно было связать с соответствующими задачами разработки и тестирования.

---

Эти атрибуты помогают обеспечить высокое качество требований, что, в свою очередь, способствует успешной разработке программного обеспечения, соответствующего ожиданиям пользователей и бизнес-целей.