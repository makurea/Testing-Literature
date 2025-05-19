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

1. Инициализация драйвера (создание сессии)
2. Выполнение тестовых команд
3. Обработка исключений (при необходимости)
4. Завершение сессии:
   - driver.quit() - корректное завершение
   - Необработанное исключение - аварийное завершение
```java
// Рекомендуемый подход:
@BeforeClass
public void setup() throws MalformedURLException {
    // Инициализация драйвера
}

@Test
public void testExample() {
    // Тестовый сценарий
}

@AfterClass
public void tearDown() {
    if (driver != null) {
        driver.quit();
    }
}
```
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