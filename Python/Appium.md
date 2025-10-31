# Содержание 📱 <a id="content"></a>          

## [🚀 Введение в Appium](#введение-в-appium)

- [Что такое Appium?](#что-такое-appium)
- [Архитектура Appium](#архитектура-appium)
- [Поддерживаемые платформы](#поддерживаемые-платформы)

## [⚙️ Настройка окружения](#настройка-окружения)

- [Установка Appium Server](#установка-appium-server)
- [Установка клиентских библиотек](#установка-клиентских-библиотек)
- [Настройка эмуляторов/симуляторов](#настройка-эмуляторов-симуляторов)
- [Настройка реальных устройств](#настройка-реальных-устройств)

## [📝 Основы работы с Appium](#основы-работы-с-appium)

- [Desired Capabilities](#desired-capabilities)
- [Инициализация драйвера](#инициализация-драйвера)
- [Базовые команды](#базовые-команды)
- [Жизненный цикл сессии](#жизненный-цикл-сессии)

## [🔍 Поиск элементов](#поиск-элементов)

- [Стратегии поиска](#стратегии-поиска)
- [XPath в Appium](#xpath-в-appium)
- [ID и Accessibility ID](#id-и-accessibility-id)
- [Цепочки поиска](#цепочки-поиска)

## [🛠️ Взаимодействие с элементами](#взаимодействие-с-элементами)

- [Клики и тапы](#клики-и-тапы)
- [Ввод текста](#ввод-текста)
- [Скроллинг](#скроллинг)
- [Жесты](#жесты)

## [📱 Особенности платформ](#особенности-платформ)

- [Android специфика](#android-специфика)
- [iOS специфика](#ios-специфика)
- [Кросс-платформенные подходы](#кросс-платформенные-подходы)

## [🧪 Тестирование с Appium](#тестирование-с-appium)

- [Интеграция с тестовыми фреймворками](#интеграция-с-тестовыми-фреймворками)
- [Логирование](#логирование)
- [Скриншоты и видео](#скриншоты-и-видео)
- [Обработка ошибок](#обработка-ошибок)

## [🚀 Продвинутые темы](#продвинутые-темы)

- [Appium Desktop](#appium-desktop)
- [Работа с гибридными приложениями](#работа-с-гибридными-приложениями)
- [Параллельный запуск](#параллельный-запуск)
- [Appium Grid](#appium-grid)

---

## Введение в Appium <a id="введение-в-appium"></a>

### Что такое Appium? <a id="что-такое-appium"></a>

Appium - это кроссплатформенный фреймворк с открытым исходным кодом для автоматизации тестирования мобильных приложений. Он позволяет писать тесты для:
- Нативных приложений (iOS, Android)
- Гибридных приложений
- Мобильных веб-приложений

Основные принципы Appium:
1. Не требует перекомпиляции приложения
2. Использует стандартные API автоматизации
3. Кроссплатформенная архитектура
4. Поддержка множества языков программирования

[🔼 К содержанию](#content)

---

### Архитектура Appium <a id="архитектура-appium"></a>

Appium имеет клиент-серверную архитектуру:

1. **Appium Server** - написан на Node.js, принимает команды от клиента
2. **Appium Clients** - библиотеки для разных языков (Python, Java, JavaScript и др.)
3. **Драйверы платформ**:
   - Android: UIAutomator2, Espresso
   - iOS: XCUITest
4. **Связующие компоненты**:
   - JSON Wire Protocol (для общения клиент-сервер)
   - WebDriver Protocol (стандартный протокол автоматизации)

Рабочий процесс:
Клиент → Appium Server → Платформенный драйвер → Устройство/Эмулятор

[🔼 К содержанию](#content)

---

### Поддерживаемые платформы <a id="поддерживаемые-платформы"></a>

Appium поддерживает следующие платформы и ОС:

**Мобильные ОС:**
- Android (4.4+)
- iOS (9.3+)
- Windows (через WinAppDriver)

**Типы приложений:**
- Нативные (собранные для конкретной платформы)
- Гибридные (WebView внутри нативного контейнера)
- Мобильные веб-приложения (браузерные)

**Языки программирования:**
- Python
- Java
- JavaScript
- Ruby
- C#
- PHP
- И другие с поддержкой WebDriver

[🔼 К содержанию](#content)

---

## Настройка окружения <a id="настройка-окружения"></a>

### Установка Appium Server <a id="установка-appium-server"></a>

### Для всех языков (требуется Node.js)

```bash
npm install -g appium
appium --version
```
[🔼 К содержанию](#content)

---

### Установка клиентских библиотек <a id="установка-клиентских-библиотек"></a>

#### Для Python:
```python
pip install Appium-Python-Client
```

#### Проверка установки:
```python
python -c "import appium; print(appium.__version__)"
```

#### Для Java (Maven):
#### Добавить в pom.xml:

```java
<dependency>
  <groupId>io.appium</groupId>
  <artifactId>java-client</artifactId>
  <version>8.0.0</version>
</dependency>
```
# Или для Gradle (build.gradle):
```java
implementation 'io.appium:java-client:8.0.0'
```
[🔼 К содержанию](#content)

---

### Настройка эмуляторов/симуляторов <a id="настройка-эмуляторов-симуляторов"></a>

#### Общее для всех:
#### Android (требуется Android Studio)

```java
sdkmanager --install "system-images;android-30;google_apis;x86"
avdmanager create avd -n Pixel_4_API_30 -k "system-images;android-30;google_apis;x86"
```

# iOS (требуется Xcode)
```swift
xcrun simctl list devices
xcrun simctl boot "iPhone 12"
```

[🔼 К содержанию](#content)

---

### Настройка реальных устройств <a id="настройка-реальных-устройств"></a>

#### Для Android:
```java
adb devices
```

#### Для iOS (требуется Mac):
```swift
idevice_id -l
```

[🔼 К содержанию](#content)

---

## Основы работы с Appium <a id="основы-работы-с-appium"></a>


// Примеры кода для Java
// Требуется: io.appium:java-client:8.0.0+

### Desired Capabilities <a id="desired-capabilities"></a>
```java
// Базовые capabilities для Android
DesiredCapabilities caps = new DesiredCapabilities();
caps.setCapability("platformName", "Android");
caps.setCapability("platformVersion", "11.0");
caps.setCapability("deviceName", "Pixel_4_API_30");
caps.setCapability("app", "/path/to/app.apk");
caps.setCapability("automationName", "UiAutomator2");

// Дополнительные параметры:
caps.setCapability("noReset", true); // Не сбрасывать состояние приложения
caps.setCapability("fullReset", false); // Полная переустановка приложения
caps.setCapability("appPackage", "com.example.app");
caps.setCapability("appActivity", ".MainActivity");
```
[🔼 К содержанию](#content)

---

### Инициализация драйвера <a id="инициализация-драйвера"></a>
```java
// Инициализация AndroidDriver
URL appiumServerUrl = new URL("http://127.0.0.1:4723/wd/hub");
AndroidDriver driver = new AndroidDriver(appiumServerUrl, caps);

// Инициализация IOSDriver (для iOS)
IOSDriver iosDriver = new IOSDriver(appiumServerUrl, caps);

// Рекомендуется использовать try-with-resources
try (AndroidDriver autoCloseableDriver = new AndroidDriver(appiumServerUrl, caps)) {
    // Тестовый код
}
```
[🔼 К содержанию](#content)

---

### Базовые команды <a id="базовые-команды"></a>

| Категория       | Команда                                                                 | Описание                                                                 | Пример использования                                                                 |
|-----------------|-------------------------------------------------------------------------|--------------------------------------------------------------------------|-------------------------------------------------------------------------------------|
| **Навигация**   | `driver.launchApp()`                                                   | Запускает приложение                                                    | `driver.launchApp();`                                                               |
|                 | `driver.closeApp()`                                                    | Закрывает приложение                                                    | `driver.closeApp();`                                                                |
|                 | `driver.resetApp()`                                                    | Сбрасывает состояние приложения                                          | `driver.resetApp();`                                                                |
|                 | `driver.activateApp("package.name")`                                   | Активирует указанное приложение                                          | `driver.activateApp("com.example.app");`                                            |
|                 | `driver.terminateApp("package.name")`                                  | Завершает указанное приложение                                           | `driver.terminateApp("com.example.app");`                                           |
|                 | `driver.startActivity("package", "activity")`                          | Запускает конкретную активность                                          | `driver.startActivity("com.example.app", ".MainActivity");`                         |
| **Элементы**    | `driver.findElement(By)`                                               | Находит элемент                                                          | `MobileElement el = (MobileElement) driver.findElement(By.id("elementId"));`        |
|                 | `element.click()`                                                      | Кликает по элементу                                                     | `element.click();`                                                                  |
|                 | `element.sendKeys("text")`                                             | Вводит текст в элемент                                                  | `element.sendKeys("Hello");`                                                        |
|                 | `element.clear()`                                                      | Очищает поле ввода                                                       | `element.clear();`                                                                  |
|                 | `element.getText()`                                                    | Получает текст элемента                                                 | `String text = element.getText();`                                                  |
|                 | `element.getAttribute("attribute")`                                    | Получает атрибут элемента                                               | `String value = element.getAttribute("content-desc");`                              |
| **Жесты**       | `driver.swipe(startX, startY, endX, endY, duration)`                   | Выполняет свайп                                                         | `driver.swipe(100, 1000, 100, 500, 1000);`                                         |
|                 | `driver.zoom(element)`                                                 | Увеличивает масштаб (зум)                                               | `driver.zoom(element);`                                                             |
|                 | `driver.pinch(element)`                                                | Уменьшает масштаб (пинч)                                               | `driver.pinch(element);`                                                            |
|                 | `driver.tap(fingers, element, duration)`                               | Тап с указанием количества пальцев                                      | `driver.tap(1, element, 500);`                                                     |
| **Системные**   | `driver.pressKey(new KeyEvent(AndroidKey.KEY))`                        | Нажимает системную кнопку                                               | `driver.pressKey(new KeyEvent(AndroidKey.HOME));`                                  |
|                 | `driver.lockDevice()`                                                  | Блокирует устройство                                                    | `driver.lockDevice();`                                                             |
|                 | `driver.unlockDevice()`                                                | Разблокирует устройство                                                 | `driver.unlockDevice();`                                                           |
|                 | `driver.isDeviceLocked()`                                              | Проверяет, заблокировано ли устройство                                  | `boolean locked = driver.isDeviceLocked();`                                         |
|                 | `driver.openNotifications()`                                           | Открывает панель уведомлений                                            | `driver.openNotifications();`                                                      |
| **Ориентация**  | `driver.rotate(ScreenOrientation)`                                     | Меняет ориентацию экрана                                                | `driver.rotate(ScreenOrientation.LANDSCAPE);`                                      |
|                 | `driver.getOrientation()`                                              | Получает текущую ориентацию                                             | `ScreenOrientation orientation = driver.getOrientation();`                         |
| **Скриншоты**   | `driver.getScreenshotAs(OutputType)`                                   | Делает скриншот                                                         | `File screenshot = driver.getScreenshotAs(OutputType.FILE);`                       |
| **Контексты**   | `driver.getContextHandles()`                                           | Получает доступные контексты (для гибридных приложений)                 | `Set<String> contexts = driver.getContextHandles();`                               |
|                 | `driver.context("contextName")`                                        | Переключает контекст                                                    | `driver.context("WEBVIEW_com.example.app");`                                       |
| **Логи**        | `driver.manage().logs().get("logType")`                                | Получает логи устройства                                                | `LogEntries logs = driver.manage().logs().get("logcat");`                          |
| **Ожидания**    | `driver.manage().timeouts().implicitlyWait(time, TimeUnit)`            | Устанавливает неявное ожидание                                          | `driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);`                 |
|                 | `new WebDriverWait(driver, timeout).until(ExpectedConditions)`         | Явное ожидание условия                                                  | `new WebDriverWait(driver, 10).until(ExpectedConditions.visibilityOf(element));`    |

[🔼 К содержанию](#content)

---

### Жизненный цикл сессии <a id="жизненный-цикл-сессии"></a>


1. **Инициализация драйвера** — создание новой сессии Appium с помощью `webdriver.Remote`.
2. **Выполнение команд** — взаимодействие с UI, валидации и утверждения (assert).
3. **Обработка исключений** — отлавливание и логирование ошибок (опционально).
4. **Завершение сессии** — вызов `driver.quit()` для корректного закрытия, даже при падении.

```python
import pytest
from appium import webdriver

@pytest.fixture(scope="class")
def driver_setup(request):
    desired_caps = {
        "platformName": "Android",
        "deviceName": "Android Emulator",
        "app": "/path/to/app.apk",
        "automationName": "UiAutomator2"
    }
    driver = webdriver.Remote("http://localhost:4723/wd/hub", desired_caps)
    request.cls.driver = driver
    yield
    driver.quit()

@pytest.mark.usefixtures("driver_setup")
class TestExample:

    def test_example(self):
        # Ваш тест здесь
        assert self.driver.is_app_installed("com.example.app")
```
| Этап                      | Описание                                                         |
|---------------------------|------------------------------------------------------------------|
| `webdriver.Remote()`      | Создание сессии и инициализация драйвера                         |
| `driver.method()`         | Выполнение тестовых шагов (например, click, send_keys)           |
| `try/except`              | Обработка исключений, если не используется фреймворк             |
| `driver.quit()`           | Завершение сессии, освобождение ресурсов                         |
| `pytest.fixture`          | Автоматизация setup/teardown логики в тестах                     |

[🔼 К содержанию](#content)

---

## Поиск элементов <a id="поиск-элементов"></a>

```python
from appium.webdriver.common.appiumby import AppiumBy
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
```

### Стратегии поиска <a id="стратегии-поиска"></a>

Основные методы поиска элементов в Appium:

1. По ID (рекомендуемый способ):
```python
element = driver.find_element(by=AppiumBy.ID, value="com.example:id/button")
```

2. По Accessibility ID:
```python
element = driver.find_element(by=AppiumBy.ACCESSIBILITY_ID, value="Login")
```

3. По XPath:
```python
element = driver.find_element(by=AppiumBy.XPATH, value="//android.widget.Button")
```

4. По классу:
```python
element = driver.find_element(by=AppiumBy.CLASS_NAME, value="android.widget.EditText")
```

5. Для Android (UiAutomator):
```python
element = driver.find_element(by=AppiumBy.ANDROID_UIAUTOMATOR,
                           'new UiSelector().text("OK")')
```
[🔼 К содержанию](#content)

---

### XPath в Appium <a id="xpath-в-appium"></a>

Примеры использования XPath:

#### Поиск по тексту
```python
element = driver.find_element(by=AppiumBy.XPATH, "//*[@text='Save']")
```
#### Поиск по частичному совпадению текста
```python
element = driver.find_element(by=AppiumBy.XPATH, "//*[contains(@text, 'av')]")
```
#### Поиск по нескольким атрибутам
```python
element = driver.find_element(by=AppiumBy.XPATH,
                           "//Button[@resource-id='btn' and @enabled='true']")
```
#### Поиск по индексу
```python
element = driver.find_element(by=AppiumBy.XPATH, "(//Button)[2]")
```

#### Поиск по иерархии
```python
element = driver.find_element(by=AppiumBy.XPATH,
                           "//LinearLayout/TextView")
```

[🔼 К содержанию](#content)

---

### ID и Accessibility ID <a id="id-и-accessibility-id"></a>

Разница между ID и Accessibility ID:

#### ID (resource-id на Android)
```python
email_field = driver.find_element(by=AppiumBy.ID, value="com.app:id/email")
```

#### Accessibility ID (content-desc на Android)
```python
password_field = driver.find_element(by=AppiumBy.ACCESSIBILITY_ID, value="password")
```
Особенности:
- ID должен быть уникальным на экране
- Accessibility ID используется для тестирования доступности
- На iOS оба метода часто используют атрибут 'name'

[🔼 К содержанию](#content)

---

### Цепочки поиска <a id="цепочки-поиска"></a>

Примеры цепочек поиска:

1. Поиск внутри элемента:
 ```python
parent = driver.find_element(by=AppiumBy.ID, value="parent")
child = parent.find_element(by=AppiumBy.CLASS_NAME, value="Button")
```
2. Поиск с ожиданием:
```python
element = WebDriverWait(driver, 10).until(
    EC.presence_of_element_located((AppiumBy.ID, "dynamic_element"))
)
```
3. Поиск нескольких элементов:
```python
buttons = driver.find_elements(by=AppiumBy.CLASS_NAME, value="Button")
buttons[0].click()
```
4. Комбинированный поиск:
```python
element = WebDriverWait(driver, 10).until(
    lambda d: d.find_element(by=AppiumBy.ID, value="parent")
              .find_element(by=AppiumBy.XPATH, value=".//Button")
)
```
[🔼 К содержанию](#content)

---

## 🛠️ Взаимодействие с элементами<a id="взаимодействие-с-элементами"></a>


### 🔘 Клики и тапы <a id="клики-и-тапы"></a>
Клики и тапы — это базовые действия пользователя, такие как нажатие на кнопку, элемент списка, ссылку и т.д.
В Appium для этого используются стандартные методы WebDriver или специальные жестовые команды.
Appium поддерживает клик как по найденному элементу, так и через координаты.
Также возможно использовать "долгий тап" (long press) и "двойной тап" — для этого применяются жестовые библиотеки, доступные в Appium.

| Команда                 | Назначение                                      |
|------------------------|-------------------------------------------------|
| `.click()`             | Стандартный клик по элементу                    |
| `TouchAction.tap()`    | Лёгкое нажатие (тап) по элементу или координатам|
| `TouchAction.long_press()` | Долгое нажатие на элемент                       |
| `TouchAction.press()` + `release()` | Базовый элементарный клик вручную       |

[🔼 К содержанию](#content)

---


### ⌨️ Ввод текста <a id="ввод-текста"></a>
Ввод текста применяется для заполнения форм, полей поиска, ввода логина и пароля и т.д.
Appium позволяет ввести текст в любой элемент, который поддерживает редактирование.
Важно учитывать, что перед вводом текста поле может потребовать очистки.
Также для некоторых полей может потребоваться фокус (клик перед вводом).
Ввод текста доступен для обеих платформ — Android и iOS.

| Команда               | Назначение                         |
|----------------------|------------------------------------|
| `.send_keys(text)`   | Ввод текста в элемент              |
| `.clear()`           | Очистка поля перед вводом          |

[🔼 К содержанию](#content)

---


### 🔃 Скроллинг <a id="скроллинг"></a>
Скроллинг используется для прокрутки списка, страницы или экрана до нужного элемента.
На Android чаще всего применяется `UiScrollable` — это встроенный механизм прокрутки.
На iOS или в кросс-платформенном подходе можно использовать свайпы (жесты), либо функции прокрутки к координатам.
Также Appium поддерживает прокрутку до элемента по тексту или другим свойствам через методы драйвера.

| Команда                                                | Назначение                                      |
|--------------------------------------------------------|-------------------------------------------------|
| `UiScrollable().scrollIntoView()`                      | Прокрутка до элемента по тексту (Android only)  |
| `driver.swipe(start_x, start_y, end_x, end_y)`         | Прокрутка по координатам (устаревший метод)     |
| `TouchAction.press().move_to().release().perform()`    | Кастомный свайп (вручную)                       |

[🔼 К содержанию](#content)

---


### 🖐️ Жесты <a id="жесты"></a>
Жесты — это взаимодействия с элементами через касания, свайпы, масштабирование и вращение.
Они особенно актуальны для мобильных приложений, где управление часто осуществляется не через клики, а через физические движения.
Appium предоставляет гибкий интерфейс для выполнения различных жестов: свайп (провести пальцем), pinch (сжать), zoom (раздвинуть), long press (долгий тап) и др.
Жесты можно выполнять относительно экрана или конкретного элемента.
Для сложных жестов используется класс TouchAction, который позволяет выстраивать цепочку действий.

| Команда                     | Назначение                                 |
|----------------------------|--------------------------------------------|
| `TouchAction.press()`      | Нажатие и удержание                        |
| `TouchAction.move_to()`    | Перемещение точки касания                 |
| `TouchAction.release()`    | Отпускание касания                        |
| `TouchAction.long_press()` | Долгий тап по элементу или координатам    |
| `driver.pinch(element)`    | Сжатие (масштабирование) элемента         |
| `driver.zoom(element)`     | Увеличение (зум) элемента                 |

[🔼 К содержанию](#content)

---

## 📱 Особенности платформ<a id="особенности-платформ"></a>


### 🤖 Android специфика <a id="android-специфика"></a>
Android предоставляет широкие возможности взаимодействия с нативными элементами, а также системными настройками.
Особенности платформы включают доступ к логам (`logcat`), использование `UIAutomator2` как наиболее стабильного драйвера, возможность прокрутки с помощью `UiScrollable` и управление разрешениями приложений.
Важно: для работы с Android необходимо включить режим разработчика и отладку по USB или настроить эмулятор.

| Особенность/Команда                         | Назначение                                               |
|--------------------------------------------|----------------------------------------------------------|
| `UIAutomator2`                              | Основной автоматизационный движок для Android            |
| `UiScrollable().scrollIntoView()`           | Поиск элемента через прокрутку списка                    |
| `adb shell`                                 | Инструмент командной строки Android для отладки         |
| `logcat`                                    | Просмотр логов устройства в реальном времени             |
| `autoGrantPermissions: true`                | Автоматическое предоставление разрешений при запуске     |

[🔼 К содержанию](#content)

---


### 🍏 iOS специфика <a id="ios-специфика"></a>
iOS требует более строгих условий для автоматизации: наличие macOS, Xcode, подписанных приложений и доступ к симулятору или реальному устройству.
В качестве движка используется `XCUITest`, поддерживающий большинство базовых действий, но ограниченный в низкоуровневом доступе.
Appium для iOS не поддерживает прямой доступ к системным настройкам, как это возможно на Android.

| Особенность/Команда                         | Назначение                                               |
|--------------------------------------------|----------------------------------------------------------|
| `XCUITest`                                  | Основной драйвер автоматизации iOS                       |
| `automationName: XCUITest`                 | Указывается в desired capabilities                       |
| `useNewWDA: true`                           | Использовать новую сессию WebDriverAgent                 |
| `wdaLocalPort`                              | Указание порта для WebDriverAgent (при параллельных тестах)|
| `simulator` / `real device`                | Поддержка как симуляторов, так и реальных устройств      |

[🔼 К содержанию](#content)

---


### 📲 Кросс-платформенные подходы <a id="кросс-платформенные-подходы"></a>
Appium позволяет использовать общий код для Android и iOS, если придерживаться универсальных стратегий поиска элементов и не привязываться к платформенно-зависимым атрибутам.
Рекомендуется использовать `accessibility id`, избегать абсолютных XPath, и выносить платформенные различия в отдельные обёртки.
Также возможна реализация Page Object модели для переиспользования логики с учётом платформ.

| Подход / Приём                     | Назначение                                                   |
|------------------------------------|--------------------------------------------------------------|
| `accessibility_id`                 | Универсальный способ поиска элементов на обеих платформах   |
| `platformName`                     | Явное указание платформы в desired capabilities              |
| `Page Object`                      | Паттерн проектирования для кросс-платформенной архитектуры   |
| `platform-specific locators`       | Разделение локаторов для Android и iOS                       |
| `if driver.capabilities['platformName'] == ...` | Условная логика по платформе                              |

[🔼 К содержанию](#content)

---

## 🧪 Тестирование с Appium<a id="тестирование-с-appium"></a>


### 🧩 Интеграция с тестовыми фреймворками <a id="интеграция-с-тестовыми-фреймворками"></a>
Appium не навязывает конкретный тестовый фреймворк — его можно интегрировать с любыми средствами автотестирования, такими как Pytest, Unittest, Nose и другими.
Наиболее популярным выбором является `pytest` из-за его гибкости, возможности параметризации, фикстур и мощной экосистемы.
Тесты с Appium пишутся как обычные UI-тесты, а создание драйвера и завершение сессии чаще всего выносится в фикстуры.

| Инструмент / Подход          | Назначение                                               |
|-----------------------------|-----------------------------------------------------------|
| `pytest`                    | Лёгкий, модульный фреймворк для написания тестов         |
| `unittest`                  | Встроенный фреймворк, используется для формальных тестов |
| `conftest.py`               | Центральное хранилище фикстур и конфигураций Pytest      |
| `pytest fixtures`           | Повторно используемые блоки кода (например, setup/teardown)|
| `markers`                   | Разметка тестов для селекции и фильтрации                |

[🔼 К содержанию](#content)

---


### 📋 Логирование <a id="логирование"></a>
Логирование — важная часть тестов с Appium, особенно при отладке.
Можно получать логи Appium-сервера, драйвера, устройства (logcat для Android) и собственные логи тестов.
Также возможна запись логов в файл для последующего анализа.
Рекомендуется логировать действия, ошибки, начало/завершение шагов и важные метаданные.

| Источник логов              | Назначение                                           |
|----------------------------|------------------------------------------------------|
| `driver.get_log('logcat')` | Получение логов Android-устройства                   |
| `driver.get_log('syslog')` | Логи iOS-устройства                                  |
| `driver.get_log('driver')` | Логи WebDriver                                       |
| `driver.get_log('server')` | Логи Appium-сервера                                  |
| `logging` (модуль Python)  | Пользовательское логирование внутри тестов           |

[🔼 К содержанию](#content)

---


### 📸 Скриншоты и видео <a id="скриншоты-и-видео"></a>
Скриншоты и видеозапись используются для визуальной фиксации состояния приложения при прохождении или падении теста.
Скриншоты можно делать вручную в нужный момент или автоматически по ошибке.
Некоторые инструменты (например, Appium + Android Emulator или iOS Simulator) позволяют снимать видео во время тестов.
Важно сохранять скриншоты и логи вместе — это упрощает диагностику багов.

| Функция / Метод                   | Назначение                                         |
|----------------------------------|----------------------------------------------------|
| `driver.get_screenshot_as_file()`| Сохранение скриншота в файл                        |
| `driver.save_screenshot()`       | Альтернативный способ сохранения скриншота         |
| `start_recording_screen()`       | Начало записи экрана (видео)                       |
| `stop_recording_screen()`        | Остановка и получение видео как base64-строки      |

[🔼 К содержанию](#content)

---


### ❌ Обработка ошибок <a id="обработка-ошибок"></a>
Обработка ошибок позволяет делать тесты стабильными и предсказуемыми.
Рекомендуется перехватывать исключения, делать скриншоты при падении, логировать ошибку и корректно завершать сессию драйвера.
Можно реализовать retry-механику или использовать `pytest-rerunfailures`.
Для управления исключениями в Python удобно использовать конструкции `try-except-finally`.

| Приём / Инструмент            | Назначение                                                  |
|------------------------------|-------------------------------------------------------------|
| `try/except/finally`         | Обработка исключений и завершение сессии                    |
| `pytest_runtest_makereport`  | Хук Pytest для действий при падении (например, скриншот)    |
| `pytest-rerunfailures`       | Повторный запуск упавших тестов                             |
| `driver.quit()`              | Закрытие сессии, даже при ошибке                            |

[🔼 К содержанию](#content)

---

## 🚀 Продвинутые темы<a id="продвинутые-темы"></a>


### 🖥️ Appium Desktop <a id="appium-desktop"></a>
Appium Desktop — это графическая оболочка для запуска Appium Server и визуального инспектирования элементов мобильного интерфейса.
Она удобна для локального тестирования, ручного запуска сессий и получения XPath/ID элементов через Inspector.
Appium Inspector позволяет подключаться к уже запущенному приложению и исследовать структуру UI в реальном времени.

| Компонент / Функция          | Назначение                                              |
|------------------------------|---------------------------------------------------------|
| Appium Server GUI            | Запуск Appium сервера с графическим интерфейсом        |
| Appium Inspector             | Инструмент визуального поиска элементов                |
| Save/Load Desired Capabilities | Сохранение и повторный запуск сессий                 |
| Start Session                | Запуск сессии для анализа интерфейса                   |
| Element details panel        | Просмотр свойств выбранного элемента                   |

[🔼 К содержанию](#content)

---


### 🧩 Работа с гибридными приложениями <a id="работа-с-гибридными-приложениями"></a>
Гибридные приложения содержат как нативные, так и веб-компоненты (например, WebView).
Appium позволяет переключаться между контекстами (NATIVE_APP и WEBVIEW) для взаимодействия с нужной частью интерфейса.
Для работы с WebView нужно включить отладку (например, `setWebContentsDebuggingEnabled(true)` в Android) и убедиться, что WebView открыт.

| Команда / Параметр              | Назначение                                                  |
|---------------------------------|-------------------------------------------------------------|
| `driver.contexts`               | Получить список доступных контекстов                        |
| `driver.context`                | Текущий активный контекст                                   |
| `driver.switch_to.context()`    | Переключение между NATIVE_APP и WEBVIEW                     |
| `chromeOptions`                 | Настройка работы с WebView на Android                       |
| `setWebContentsDebuggingEnabled`| Включение отладки WebView в Android                         |

[🔼 К содержанию](#content)

---


### 🧵 Параллельный запуск <a id="параллельный-запуск"></a>
Параллельное выполнение тестов позволяет ускорить прогон и запускать автотесты одновременно на нескольких устройствах или конфигурациях.
Для этого каждому драйверу нужно задать уникальные порты (`systemPort` для Android, `wdaLocalPort` для iOS), а сами тесты запускать в отдельных потоках или процессах.
Pytest поддерживает параллельный запуск с помощью `pytest-xdist`.

| Параметр / Инструмент          | Назначение                                                  |
|-------------------------------|-------------------------------------------------------------|
| `systemPort`                  | Уникальный порт для Android драйвера                        |
| `wdaLocalPort`                | Уникальный порт для iOS WebDriverAgent                      |
| `pytest-xdist`                | Расширение Pytest для параллельного запуска                 |
| `-n auto`                     | Параллельный запуск на доступное количество ядер            |
| `threading/multiprocessing`   | Механизмы многопоточности в Python                          |

[🔼 К содержанию](#content)

---


### 🌐 Appium Grid <a id="appium-grid"></a>
Appium Grid (аналог Selenium Grid) позволяет распределённо запускать тесты на разных машинах и устройствах, централизованно управляя инстансами Appium.
Обычно используется для масштабирования тестов и CI/CD-интеграции.
Grid состоит из хаба (центрального управляющего сервера) и нодов (машин с реальными устройствами или эмуляторами).

| Компонент / Понятие            | Назначение                                                  |
|-------------------------------|-------------------------------------------------------------|
| Appium Node                   | Отдельный инстанс Appium, работающий с конкретным устройством |
| Selenium Grid Hub             | Центральный сервер, распределяющий задачи                   |
| Appium Grid Plugin            | Плагин для поддержки Appium в инфраструктуре Selenium Grid  |
| Remote WebDriver              | Драйвер для подключения к удалённому Appium                 |
| Docker + Appium              | Используется для создания контейнеризированных нодов        |

[🔼 К содержанию](#content)

---

