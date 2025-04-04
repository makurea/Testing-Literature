# Содержание 🌍 <a id="content"></a> 
  
## 🔷 [Введение](#введение)       
 
- [Самопрезентация](#самопрезентация)  
- [Рассказать про команду](#рассказать-про-команду)  

## 🔷 [Основы тестирования](#основы-тестирования)  

- [Что такое тестирование?](#что-такое-тестирование)  
- [Какие критерии завершения тестирования?](#какие-критерии-завершения-тестирования)  

## 🔷 [Методологии разработки](#методологии-разработки)  

- [Scrum: основные принципы](#scrum-основные-принципы)  
- [Количество участников в Scrum-команде и почему?](#количество-участников-в-scrum-команде-и-почему)  

## 🔷 [Контроль версий (Git)](#контроль-версий-git)  

- [Git: основные команды](#git-основные-команды)  

## 🔷 [CI/CD и автоматизация процессов](#ci-cd-и-автоматизация-процессов)  

- [Что такое CI/CD?](#что-такое-ci-cd)   
- [**Jenkins:** Как запускать тесты по времени и событиям](#как-запускать-тесты-по-времени-и-событиям-в-jenkins)  
- [**Jenkins:** Настройка в Jenkins](#настройка-в-jenkins)  
- [**Сборщики проектов:** Gradle](#gradle)  
- [**Сборщики проектов:** Maven](#maven)  

## 🔷 [Автоматизированное тестирование](#автоматизированное-тестирование) 

  - [**Test Runner:** JUnit / TestNG (аннотации)](#junit-testng-аннотации)   
  - [**Веб-тестирование:** Selenium / Selenide (основные классы)](#selenium-selenide-основные-классы)  
  - [Локаторы](#локаторы)    
  - [**BDD (поведенческое тестирование):** Cucumber в общих чертах](#cucumber-в-общих-чертах)  

## 🔷 [Тестирование API](#тестирование-api)  

  - [**Ожидания в API-тестах:** Библиотеки для ожиданий](#библиотеки-для-ожиданий-в-api-тестах)    
  - [Когда мы сожем сказать что приложение **RestFull**?](#приложение-RestFull)
  - [**REST / SOAP:** Методы, идемпотентность](#rest-soap-методы-идемпотентность)
  - [**SOAP** Какой http метод использует soap?](#http-метод)

## 🔷 [Инфраструктура и DevOps](#инфраструктура-и-devops)  

  - [**Контейнеризация / Виртуализация:** Что это такое и в чем разница?](#контейнеризация-виртуализация)   
  - [**Брокеры сообщений:** Что это и зачем используется?](#брокеры-сообщений)  

## 🔷 [Тестирование производительности](#тестирование-производительности)  
 
  - [**Нагрузочное тестирование:** Что это и как проводится?](#нагрузочное-тестирование)  


## 🔷 Введение <a id="введение"></a>
## Самопрезентация <a id="самопрезентация"></a>

в процессе...📝

[К содержанию](#content)

---

## Рассказать про команду <a id="рассказать-про-команду"></a>

Моя команда состоит из различных специалистов, работающих совместно для достижения общей цели — выпуска качественного программного продукта.  
Типичная команда разработки включает:

- **Разработчиков** — пишут код, реализуют новый функционал, исправляют баги.
- **Тестировщиков** — проверяют продукт, находят ошибки, создают тест-кейсы.
- **Аналитиков** — собирают и анализируют требования, помогают формировать задачи.
- **DevOps-инженеров** — занимаются автоматизацией развертывания, поддержкой инфраструктуры.
- **Менеджеров проекта / Scrum-мастера** — организуют процесс, контролируют выполнение задач, управляют рисками.

Мы работаем в Agile-процессе, например, Scrum, где взаимодействие между членами команды играет ключевую роль.

[К содержанию](#content)

---

## 🔷 Основы тестирования <a id="основы-тестирования"></a>

## Что такое тестирование? <a id="что-такое-тестирование"></a>

Тестирование — это процесс проверки программного обеспечения на соответствие требованиям и выявление возможных дефектов.  
Оно направлено на улучшение качества продукта и снижение рисков, связанных с его использованием.

### Основные цели тестирования:
- Обнаружение и предотвращение ошибок;
- Проверка соответствия требованиям;
- Оценка надежности, безопасности и производительности системы;
- Уверенность в работоспособности продукта.

### Виды тестирования:
- **Функциональное** (проверка работы системы по требованиям);
- **Нефункциональное** (производительность, безопасность, удобство использования);
- **Ручное** (выполняется тестировщиком);
- **Автоматизированное** (с использованием инструментов и скриптов).

[К содержанию](#content)

---

## Какие критерии завершения тестирования? <a id="какие-критерии-завершения-тестирования"></a>

Критерии завершения тестирования — это условия, при выполнении которых можно считать, что тестирование завершено.

### Основные критерии завершения:
- Достигнуто требуемое **покрытие тестами** (например, 80% функционала протестировано);
- Исполнены все **критические тест-кейсы**;
- Все найденные **критические баги исправлены** и повторно протестированы;
- Количество оставшихся багов не превышает **допустимый порог** (например, нет блокирующих или критических дефектов);
- Проведены **финальные приемочные тесты**;
- Составлена **итоговая документация** (отчет по тестированию).

Тестирование завершается после совместного решения команды и заинтересованных лиц.

[К содержанию](#content)

---

## 🔷 Методологии разработки <a id="методологии-разработки"></a>

## Scrum: основные принципы <a id="scrum-основные-принципы"></a>
Scrum — это популярная гибкая методология разработки ПО, основанная на следующих принципах:

- **Итеративность** — работа ведется короткими циклами (спринтами) длительностью 1-4 недели
- **Прозрачность** — все участники имеют доступ к информации о процессе и прогрессе
- **Инспекция** — регулярный анализ результатов для выявления отклонений
- **Адаптация** — постоянная корректировка процессов для повышения эффективности

Ключевые элементы Scrum:
- **Product Backlog** — упорядоченный список всех требований к продукту
- **Sprint Backlog** — задачи, запланированные для выполнения в текущем спринте
- **Daily Scrum** — ежедневные короткие встречи для синхронизации команды
- **Sprint Review** — демонстрация результатов спринта заинтересованным лицам
- **Sprint Retrospective** — анализ прошедшего спринта и поиск улучшений процесса

[К содержанию](#content)

---

## Количество участников в Scrum-команде и почему? <a id="количество-участников-в-scrum-команде-и-почему"></a>
Оптимальное количество участников в Scrum-команде составляет **7±2 человека** (от 5 до 9).

Причины такого ограничения:
- **Коммуникационная эффективность** — количество коммуникационных каналов растет экспоненциально с увеличением размера команды по формуле n(n-1)/2
- **Повышение продуктивности** — в небольших командах выше уровень вовлеченности и ответственности
- **Самоорганизация** — легче координировать работу и принимать решения в команде ограниченного размера
- **Снижение накладных расходов** — меньше времени тратится на коммуникацию и согласования

Состав Scrum-команды:
- **Product Owner** (1 человек) — представляет интересы стейкхолдеров, управляет бэклогом
- **Scrum Master** (1 человек) — обеспечивает следование процессам, устраняет препятствия
- **Development Team** (3-7 человек) — кросс-функциональная команда, реализующая задачи

[К содержанию](#content)

---

## 🔷 Контроль версий (Git) <a id="контроль-версий-git"></a>

## Git: основные команды <a id="git-основные-команды"></a>
Git — распределенная система контроля версий для эффективной работы с исходным кодом. Основные команды:

**Начало работы:**
- `git init` — создать новый репозиторий в текущей директории
- `git clone <url>` — скопировать удаленный репозиторий на локальный компьютер

**Основные операции:**
- `git status` — показать статус рабочей директории и индекса
- `git add <file>` — добавить файл в индекс для коммита
- `git add .` — добавить все изменения в индекс
- `git commit -m "сообщение"` — создать коммит с изменениями из индекса
- `git log` — просмотр истории коммитов

**Работа с ветками:**
- `git branch` — просмотр списка веток
- `git branch <name>` — создание новой ветки
- `git checkout <branch>` — переключение на другую ветку
- `git checkout -b <branch>` — создание и переключение на новую ветку
- `git merge <branch>` — слияние указанной ветки с текущей

**Работа с удаленными репозиториями:**
- `git remote add <name> <url>` — добавить удаленный репозиторий
- `git push <remote> <branch>` — отправить изменения в удаленный репозиторий
- `git pull <remote> <branch>` — получить и интегрировать изменения из удаленного репозитория
- `git fetch <remote>` — получить изменения из удаленного репозитория без слияния

**Дополнительные команды:**
- `git stash` — временно сохранить незафиксированные изменения
- `git reset <file>` — отменить добавление файла в индекс
- `git reset --hard <commit>` — вернуть репозиторий к определенному коммиту
- `git rebase <branch>` — перенести изменения текущей ветки на верхушку указанной ветки

[К содержанию](#content)

---

## 🔷 CI/CD и автоматизация процессов <a id="ci-cd-и-автоматизация-процессов"></a>
## Что такое CI/CD? <a id="что-такое-ci-cd"></a>
CI/CD (Continuous Integration/Continuous Delivery) — набор практик, направленных на автоматизацию процесса разработки и доставки программного обеспечения.

**Continuous Integration (Непрерывная интеграция):**
- Автоматическая сборка и тестирование кода при каждом изменении
- Раннее обнаружение проблем интеграции
- Постоянная проверка качества кода
- Быстрая обратная связь для разработчиков

**Continuous Delivery (Непрерывная доставка):**
- Автоматическая подготовка кода к развертыванию
- Возможность в любой момент выпустить стабильную версию
- Снижение рисков при релизе

**Continuous Deployment (Непрерывное развертывание):**
- Автоматическое развертывание изменений в продакшн
- Минимальное время между написанием кода и появлением функциональности у пользователей

**Ключевые компоненты CI/CD:**
- Система контроля версий (Git)
- Сервер непрерывной интеграции (Jenkins, GitLab CI, TeamCity)
- Автоматические тесты (модульные, интеграционные, функциональные)
- Инструменты сборки проектов (Maven, Gradle)
- Средства управления конфигурацией (Ansible, Chef, Puppet)
- Мониторинг и обратная связь


[К содержанию](#content)

---

## **Jenkins:** Как запускать тесты по времени и событиям в Jenkins <a id="как-запускать-тесты-по-времени-и-событиям-в-jenkins"></a>
Jenkins позволяет настраивать запуск тестов как по расписанию, так и в ответ на определенные события:

**Запуск по расписанию (время):**
- **Cron-выражения** — основной механизм настройки расписания в Jenkins
- **Синтаксис:** `МИНУТЫ ЧАСЫ ДЕНЬ_МЕСЯЦА МЕСЯЦ ДЕНЬ_НЕДЕЛИ`
- **Примеры:**
 - `0 12 * * *` — запуск ежедневно в 12:00
 - `0 9 * * 1-5` — запуск в 9:00 с понедельника по пятницу
 - `0 */4 * * *` — запуск каждые 4 часа
 - `H/15 * * * *` — запуск каждые 15 минут (с распределением нагрузки)

**Запуск по событиям:**
- **Webhook-триггеры:**
 - После push в репозиторий (через Git/SVN hooks)
 - После создания Pull/Merge Request
 - При изменении статуса связанных задач
- **Зависимости между задачами:**
 - После успешного выполнения другой задачи
 - После сборки upstream-проектов
- **Ручные триггеры:**
 - Кнопка "Build Now" в интерфейсе
 - Запуск через Jenkins API
- **Другие триггеры:**
 - SCM polling — периодическая проверка изменений в репозитории
 - При получении сообщения от внешней системы

**Настройка триггеров в Jenkins:**
- В конфигурации задачи выбрать раздел "Build Triggers"
- Для cron-расписания использовать опцию "Build periodically"
- Для событий от GitHub/GitLab выбрать соответствующий webhook-триггер
- Для комплексных сценариев можно использовать плагин Pipeline и Jenkinsfile

**Лучшие практики:**
- Использовать параметр "H" для распределения нагрузки на сервер
- Комбинировать разные типы триггеров для оптимальной работы
- Избегать слишком частых запусков ресурсоемких тестов
- Настраивать уведомления о результатах запусков

[К содержанию](#content)

---

## **Jenkins:** Настройка в Jenkins <a id="настройка-в-jenkins"></a>
Jenkins — это инструмент непрерывной интеграции с широкими возможностями конфигурации:

**Базовая настройка Jenkins:**
- **Системные настройки** (Manage Jenkins → Configure System):
 - Настройка JDK, Git, Maven, Gradle
 - Конфигурация email-уведомлений
 - Настройка безопасности и прав доступа
 - Конфигурация глобальных переменных окружения
 - Интеграция с внешними системами

**Создание и настройка задач (джобов):**
- **Типы задач:**
 - Freestyle project — простая настройка через UI
 - Pipeline — настройка через код (Jenkinsfile)
 - Multibranch Pipeline — автоматическое определение веток из репозитория
 - Matrix Project — для запуска задач в различных конфигурациях

**Конфигурация Freestyle-задачи:**
1. **Source Code Management** — подключение к репозиторию (Git, SVN)
2. **Build Triggers** — настройка запуска (по времени, событиям)
3. **Build Environment** — подготовка среды для сборки
4. **Build Steps** — этапы сборки (скрипты, команды)
5. **Post-build Actions** — действия после сборки (публикация отчетов, уведомления)

**Настройка Pipeline:**
- Написание Jenkinsfile (Groovy DSL) с описанием этапов:
 ```groovy
 pipeline {
     agent any
     stages {
         stage('Build') { steps { ... } }
         stage('Test') { steps { ... } }
         stage('Deploy') { steps { ... } }
     }
     post {
         always { ... }
         success { ... }
         failure { ... }
     }
 }
```

[К содержанию](#content)

---




## Какой http метод использует soap? <a id="http-метод"></a>

SOAP (Simple Object Access Protocol) обычно **работает поверх протоколов HTTP или HTTPS**, 
но не зависит от конкретных методов HTTP, как это делают RESTful сервисы. Вместо этого запросы SOAP,
как правило, выполняются **с использованием метода POST**, где SOAP-сообщение включается в тело HTTP-запроса. 
Это инкапсулированное сообщение содержит всю необходимую информацию для обработки запроса SOAP и отправки ответа.


[К содержанию](#content)

---

## Когда мы сожем сказать что приложение RestFull? <a id="приложение-RestFull"></a>

Приложение можно считать RESTful, если оно основано на **клиент-серверной архитектуре**,  
использует **stateless-взаимодействие** (означает, что сервер не хранит состояние клиента между запросами — каждый запрос самодостаточен),  
имеет **единообразный интерфейс** (URL-адреса для ресурсов),  
поддерживает **кэширование, слойность** и **коды состояния HTTP** для передачи информации.


[К содержанию](#content)

---
