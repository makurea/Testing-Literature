# Содержание 
 
- **Строки**
  - [🟢 Методы класса String](#metods-string)  
  - [🟢 Классы для работы со строками](#class-string)  

- **Массивы**
  - [🟡 Методы класса Arrays](#metods-arrays)  
  - [🟡 Классы и интерфейсы для работы с Arrays](#class-arrays)  

- **Списки**
  - [🔵 Методы класса List](#metods-list)  
  - [🔵 Классы и интерфейсы для работы с List](#class-list)  

- **Множества**
  - [🟣 Методы класса Set](#metods-set)  
  - [🟣 Классы и интерфейсы для работы с Set](#class-set)  

- **Отображения**
  - [🟤 Методы класса Map](#metods-map)  
  - [🟤 Классы и интерфейсы для работы с Map](#class-map)  

- **Математика**
  - [⭕ Методы класса Math](#metods-math)  
  - [⭕ Классы и интерфейсы для работы с Math](#class-math)  

- **Числа**
  - [🟠 Методы классов Integer и Double](#metods-integer-double)  
  - [🟠 Классы для работы с Integer и Double](#class-integer-double)  

## <a name="metods-string"></a>🟢Методы класса String в Java 

| Метод | Описание |
|--------|----------|
| `charAt(int index)` | Возвращает символ по указанному индексу. |
| `compareTo(String anotherString)` | Сравнивает две строки лексикографически. |
| `compareToIgnoreCase(String str)` | Сравнивает строки без учета регистра. |
| `concat(String str)` | Объединяет две строки. |
| `contains(CharSequence s)` | Проверяет, содержит ли строка указанную последовательность символов. |
| `contentEquals(CharSequence cs)` | Проверяет, равна ли строка указанной последовательности символов. |
| `endsWith(String suffix)` | Проверяет, заканчивается ли строка указанным суффиксом. |
| `equals(Object anObject)` | Сравнивает строки на равенство. |
| `equalsIgnoreCase(String anotherString)` | Сравнивает строки на равенство без учета регистра. |
| `format(String format, Object... args)` | Возвращает отформатированную строку. |
| `getBytes()` | Преобразует строку в массив байтов. |
| `indexOf(int ch)` | Возвращает индекс первого вхождения указанного символа. |
| `indexOf(String str)` | Возвращает индекс первого вхождения указанной подстроки. |
| `isEmpty()` | Проверяет, является ли строка пустой. |
| `lastIndexOf(int ch)` | Возвращает индекс последнего вхождения указанного символа. |
| `length()` | Возвращает длину строки. |
| `replace(char oldChar, char newChar)` | Заменяет все вхождения одного символа на другой. |
| `replaceAll(String regex, String replacement)` | Заменяет все совпадения с регулярным выражением. |
| `split(String regex)` | Разбивает строку на массив подстрок. |
| `startsWith(String prefix)` | Проверяет, начинается ли строка с указанного префикса. |
| `substring(int beginIndex)` | Возвращает подстроку, начиная с указанного индекса. |
| `substring(int beginIndex, int endIndex)` | Возвращает подстроку между указанными индексами. |
| `toCharArray()` | Преобразует строку в массив символов. |
| `toLowerCase()` | Преобразует строку в нижний регистр. |
| `toUpperCase()` | Преобразует строку в верхний регистр. |
| `trim()` | Удаляет начальные и конечные пробелы. |

# <a name="class-string"></a>🟢Классы для работы со строками в Java

| Класс | Описание |
|-------|----------|
| `String` | Несменяемый (immutable) класс для представления строк. |
| `StringBuilder` | Класс для создания и изменения строк с высокой производительностью (не синхронизирован). |
| `StringBuffer` | Аналогичен `StringBuilder`, но синхронизирован (потокобезопасен). |
| `Pattern` | Используется для определения регулярных выражений. |
| `Matcher` | Используется вместе с `Pattern` для выполнения операций сопоставления. |
| `Formatter` | Предоставляет функциональность форматирования строк. |
| `MessageFormat` | Поддерживает форматирование строк с использованием шаблонов. |
| `DecimalFormat` | Предназначен для форматирования чисел и валют. |
| `Collator` | Используется для сравнения строк с учетом локали. |
| `Normalizer` | Предоставляет методы для нормализации текста Unicode. |
| `CharSequence` | Интерфейс, который реализует класс `String` и другие классы для представления последовательности символов. |
| `StringTokenizer` | Класс для разбиения строки на токены (устаревший, рекомендуется использовать `split()`). |
| `CharBuffer` | Часть пакета `java.nio`, представляет буфер символов. |
| `ByteBuffer` | Часть пакета `java.nio`, используется для работы с байт-буферами при преобразовании строк. |
| `Charset` | Представляет набор символов и способы их кодирования/декодирования. |
| `CoderResult` | Используется при кодировании/декодировании строк для обработки ошибок. |
| `CharsetEncoder` | Используется для кодирования строк в байты. |
| `CharsetDecoder` | Используется для декодирования байтов в строки. |

---

# <a name="metods-arrays"></a>🟡Методы класса Arrays 

| Метод | Описание |
|--------|----------|
| `asList(T... a)` | Преобразует массив в список. |
| `binarySearch(int[] a, int key)` | Выполняет бинарный поиск в отсортированном массиве. |
| `copyOf(int[] original, int newLength)` | Создает копию массива с новой длиной. |
| `copyOfRange(int[] original, int from, int to)` | Создает копию части массива. |
| `equals(int[] a, int[] a2)` | Проверяет массивы на равенство. |
| `fill(int[] a, int val)` | Заполняет массив указанным значением. |
| `sort(int[] a)` | Сортирует массив целых чисел. |
| `sort(T[] a)` | Сортирует массив объектов, реализующих Comparable. |
| `toString(int[] a)` | Преобразует массив в строку. |

# <a name="class-arrays"></a>🟡Классы и интерфейсы для работы с массивами

| Класс/Интерфейс | Описание |
|-----------------|----------|
| `Arrays` | Предоставляет статические методы для работы с массивами, такие как сортировка, поиск, копирование и сравнение. |
| `ArrayList` | Реализация динамического массива, которая может расти и уменьшаться во время выполнения. |
| `Array` | Класс из пакета `java.lang.reflect`, используется для создания и обращения к массивам через рефлексию. |
| `Vector` | Устаревший класс, аналог `ArrayList`, но синхронизированный (потокобезопасный). |
| `LinkedList` | Реализация списка на основе двусвязного списка, также может использоваться как динамический массив. |
| `Collections` | Предоставляет статические методы для работы с коллекциями, включая массивы, такие как сортировка, поиск и преобразование. |
| `List` | Интерфейс, представляющий упорядоченный список элементов, который может содержать дубликаты. |
| `Set` | Интерфейс, представляющий коллекцию без дублирующихся элементов. |
| `HashSet` | Реализация интерфейса `Set`, основанная на хеш-таблице. |
| `LinkedHashSet` | Реализация `Set`, сохраняющая порядок вставки элементов. |
| `TreeSet` | Реализация `Set`, автоматически сортирующая элементы. |
| `Stream` | Представляет последовательность элементов, поддерживающую функциональные операции, такие как фильтрация, отображение и сортировка. |
| `Spliterator` | Используется для параллельной обработки элементов массива или коллекции. |
| `PriorityQueue` | Коллекция, основанная на приоритетной очереди, где элементы организованы по их приоритету. |
| `Stack` | Реализация стека на основе класса `Vector`. |
| `Deque` | Интерфейс, представляющий двустороннюю очередь, поддерживающую добавление и удаление элементов с обоих концов. |
| `ArrayDeque` | Реализация интерфейса `Deque`, используемая для эффективной работы со стеками и очередями. |
| `AbstractList` | Абстрактный класс, предоставляющий базовую реализацию интерфейса `List`. |
| `AbstractCollection` | Абстрактный класс, предоставляющий базовую реализацию интерфейса `Collection`. |

---

# <a name="metods-list"></a>🔵Методы класса List

| Метод | Описание |
|--------|----------|
| `add(E e)` | Добавляет элемент в список. |
| `add(int index, E element)` | Вставляет элемент в указанную позицию. |
| `clear()` | Очищает список. |
| `contains(Object o)` | Проверяет, содержится ли элемент в списке. |
| `get(int index)` | Получает элемент по индексу. |
| `indexOf(Object o)` | Возвращает индекс первого вхождения элемента. |
| `isEmpty()` | Проверяет, пуст ли список. |
| `iterator()` | Возвращает итератор списка. |
| `lastIndexOf(Object o)` | Возвращает индекс последнего вхождения элемента. |
| `remove(int index)` | Удаляет элемент по индексу. |
| `remove(Object o)` | Удаляет первое вхождение указанного элемента. |
| `set(int index, E element)` | Заменяет элемент в указанной позиции. |
| `size()` | Возвращает размер списка. |
| `subList(int fromIndex, int toIndex)` | Возвращает подсписок. |
| `toArray()` | Преобразует список в массив. |

# <a name="class-list"></a>🔵Классы и интерфейсы для работы со списками (List)

| Класс/Интерфейс | Описание |
|-----------------|----------|
| `List` | Интерфейс, представляющий упорядоченный список элементов, который может содержать дубликаты. |
| `ArrayList` | Реализация интерфейса `List`, основанная на динамическом массиве. Позволяет быстрый случайный доступ к элементам, но медленное добавление/удаление в середине списка. |
| `LinkedList` | Реализация интерфейса `List`, основанная на двусвязном списке. Подходит для частого добавления/удаления элементов, но медленный случайный доступ. |
| `Vector` | Устаревший класс, аналог `ArrayList`, но синхронизированный (потокобезопасный). |
| `Stack` | Реализация стека, основанная на классе `Vector`. Предоставляет методы для работы со стеком (LIFO - Last In, First Out). |
| `AbstractList` | Абстрактный класс, предоставляющий базовую реализацию интерфейса `List`. Используется как базовый класс для создания собственных реализаций списков. |
| `CopyOnWriteArrayList` | Потокобезопасная реализация интерфейса `List`, которая создает новую копию массива при каждом изменении. Полезна в многопоточных средах, где чтение происходит чаще, чем запись. |
| `SubList` | Временный представитель подсписка, создаваемый методом `subList(int fromIndex, int toIndex)` класса `ArrayList` или других реализаций `List`. |
| `RandomAccess` | Маркерный интерфейс, указывающий, что реализация `List` поддерживает быстрый случайный доступ к элементам (например, `ArrayList`). |
| `Deque` | Интерфейс, представляющий двустороннюю очередь, который также может использоваться как список. |
| `ArrayDeque` | Реализация интерфейса `Deque`, которая может использоваться как список, стек или очередь. |
| `ListIterator` | Интерфейс, расширяющий функциональность `Iterator`, позволяющий перемещаться по списку вперед и назад, а также модифицировать его во время итерации. |

---

# <a name="metods-set"></a>🟣Методы класса Set  

| Метод | Описание |
|--------|----------|
| `add(E e)` | Добавляет элемент в множество. |
| `clear()` | Очищает множество. |
| `contains(Object o)` | Проверяет, содержится ли элемент в множестве. |
| `isEmpty()` | Проверяет, пусто ли множество. |
| `iterator()` | Возвращает итератор множества. |
| `remove(Object o)` | Удаляет элемент из множества. |
| `size()` | Возвращает размер множества. |
| `toArray()` | Преобразует множество в массив. |

# <a name="class-set"></a>🟣Классы и интерфейсы для работы с Set

| Класс/Интерфейс | Описание |
|-----------------|----------|
| `Set` | Интерфейс, представляющий коллекцию без дублирующихся элементов. Элементы не имеют определенного порядка (кроме специализированных реализаций). |
| `HashSet` | Реализация интерфейса `Set`, основанная на хеш-таблице. Не гарантирует порядок элементов. |
| `LinkedHashSet` | Реализация интерфейса `Set`, сохраняющая порядок вставки элементов. Комбинирует функциональность хеш-таблицы и связанного списка. |
| `TreeSet` | Реализация интерфейса `Set`, автоматически сортирующая элементы в естественном порядке или по заданному компаратору. |
| `EnumSet` | Специализированная реализация `Set`, предназначенная для работы с перечислениями (`enum`). Эффективна по памяти и производительности. |
| `AbstractSet` | Абстрактный класс, предоставляющий базовую реализацию интерфейса `Set`. Используется как основа для создания собственных реализаций множеств. |
| `NavigableSet` | Расширяет интерфейс `SortedSet`, добавляя методы для навигации (например, поиск ближайшего элемента). |
| `SortedSet` | Интерфейс, представляющий отсортированное множество. Гарантирует, что элементы хранятся в определенном порядке. |
| `ConcurrentSkipListSet` | Потокобезопасная реализация интерфейса `NavigableSet`, основанная на пропускном списке. Подходит для многопоточных приложений. |
| `Collections.unmodifiableSet` | Метод, возвращающий неизменяемое представление множества. |
| `Collections.synchronizedSet` | Метод, возвращающий потокобезопасное обертывание множества. |

---

# <a name="metods-map"></a>🟤Методы класса Map 

| Метод | Описание |
|--------|----------|
| `clear()` | Очищает карту. |
| `containsKey(Object key)` | Проверяет наличие ключа. |
| `containsValue(Object value)` | Проверяет наличие значения. |
| `entrySet()` | Возвращает множество пар ключ-значение. |
| `get(Object key)` | Получает значение по ключу. |
| `isEmpty()` | Проверяет, пуста ли карта. |
| `keySet()` | Возвращает множество ключей. |
| `put(K key, V value)` | Добавляет пару ключ-значение. |
| `putAll(Map<? extends K, ? extends V> m)` | Добавляет все элементы из другой карты. |
| `remove(Object key)` | Удаляет элемент по ключу. |
| `size()` | Возвращает размер карты. |
| `values()` | Возвращает коллекцию значений. |

# <a name="class-map"></a>🟤Классы и интерфейсы для работы с Map

| Класс/Интерфейс | Описание |
|-----------------|----------|
| `Map` | Интерфейс, представляющий коллекцию пар "ключ-значение", где каждый ключ уникален. |
| `HashMap` | Реализация интерфейса `Map`, основанная на хеш-таблице. Не гарантирует порядок элементов. |
| `LinkedHashMap` | Реализация интерфейса `Map`, сохраняющая порядок вставки элементов. Может также поддерживать порядок доступа (LRU - Least Recently Used). |
| `TreeMap` | Реализация интерфейса `Map`, автоматически сортирующая ключи в естественном порядке или по заданному компаратору. |
| `Hashtable` | Устаревшая реализация интерфейса `Map`, синхронизированная (потокобезопасная). Не допускает `null` ключей и значений. |
| `WeakHashMap` | Реализация интерфейса `Map`, где ссылки на ключи слабые (weak), что позволяет сборщику мусора удалять записи, если ключ больше не используется. |
| `IdentityHashMap` | Реализация интерфейса `Map`, где сравнение ключей происходит через оператор `==`, а не через метод `equals`. |
| `EnumMap` | Специализированная реализация `Map`, предназначенная для работы с перечислениями (`enum`) как ключами. Эффективна по памяти и производительности. |
| `ConcurrentHashMap` | Потокобезопасная реализация интерфейса `Map`, оптимизированная для многопоточных приложений. |
| `AbstractMap` | Абстрактный класс, предоставляющий базовую реализацию интерфейса `Map`. Используется как основа для создания собственных реализаций отображений. |
| `NavigableMap` | Расширяет интерфейс `SortedMap`, добавляя методы для навигации (например, поиск ближайшего элемента). |
| `SortedMap` | Интерфейс, представляющий отсортированное отображение. Гарантирует, что ключи хранятся в определенном порядке. |
| `Collections.unmodifiableMap` | Метод, возвращающий неизменяемое представление отображения. |
| `Collections.synchronizedMap` | Метод, возвращающий потокобезопасное обертывание отображения. |
| `Properties` | Подкласс `Hashtable`, предназначенный для хранения наборов свойств (например, конфигурационных параметров). |

---

# <a name="metods-math"></a>⭕Методы класса Math 

| Метод | Описание |
|--------|----------|
| `abs(int a)` | Возвращает модуль числа. |
| `ceil(double a)` | Округляет число вверх. |
| `cos(double a)` | Вычисляет косинус угла. |
| `floor(double a)` | Округляет число вниз. |
| `max(int a, int b)` | Возвращает большее из двух чисел. |
| `min(int a, int b)` | Возвращает меньшее из двух чисел. |
| `pow(double a, double b)` | Возводит число в степень. |
| `random()` | Возвращает случайное число от 0.0 до 1.0. |
| `round(double a)` | Округляет число до ближайшего целого. |
| `sin(double a)` | Вычисляет синус угла. |
| `sqrt(double a)` | Возвращает квадратный корень числа. |
| `tan(double a)` | Вычисляет тангенс угла. |

# <a name="class-math"></a>⭕Классы и интерфейсы для работы с математическими операциями

| Класс/Интерфейс | Описание |
|-----------------|----------|
| `Math` | Класс, предоставляющий статические методы для выполнения базовых математических операций, таких как округление, возведение в степень, вычисление корней, тригонометрические функции и другие. |
| `StrictMath` | Аналогичен классу `Math`, но гарантирует строгую портируемость результатов между разными платформами. |
| `BigInteger` | Класс для представления произвольно больших целых чисел. Поддерживает арифметические операции без ограничений на размер числа. |
| `BigDecimal` | Класс для представления чисел с плавающей точкой с произвольной точностью. Используется для финансовых и точных вычислений. |
| `Random` | Класс для генерации псевдослучайных чисел. Предоставляет методы для получения случайных целых чисел, вещественных чисел, битов и других типов данных. |
| `SecureRandom` | Подкласс `Random`, предназначенный для генерации криптографически надежных случайных чисел. |
| `BitSet` | Класс для работы с наборами битов, который может использоваться для представления целых чисел или множеств. Поддерживает логические операции (AND, OR, XOR). |
| `DoubleSummaryStatistics` | Класс для сбора статистики по набору чисел с плавающей точкой (например, минимум, максимум, среднее значение). |
| `IntSummaryStatistics` | Класс для сбора статистики по набору целых чисел. |
| `LongSummaryStatistics` | Класс для сбора статистики по набору длинных целых чисел. |
| `SplittableRandom` | Введенный в Java 8 класс для генерации случайных чисел, поддерживающий параллельную работу за счет создания подгенераторов. |
| `DecimalFormat` | Класс для форматирования чисел, валют и процентов. Позволяет контролировать формат вывода чисел. |
| `NumberFormat` | Абстрактный класс, предоставляющий методы для форматирования и анализа чисел, валют и процентов в зависимости от локали. |
| `RoundingMode` | Перечисление, определяющее стратегии округления для операций с числами, особенно с `BigDecimal`. |

---

# <a name="metods-integer-double"></a>🟠Методы классов Integer и Double

| Метод | Описание |
|--------|----------|
| `byteValue()` | Преобразует в `byte`. |
| `compare(int x, int y)` | Сравнивает два `int`. |
| `compare(double x, double y)` | Сравнивает два `double`. |
| `doubleValue()` | Преобразует в `double`. |
| `equals(Object obj)` | Проверяет равенство объектов. |
| `floatValue()` | Преобразует в `float`. |
| `intValue()` | Преобразует в `int`. |
| `longValue()` | Преобразует в `long`. |
| `parseDouble(String s)` | Преобразует строку в `double`. |
| `parseInt(String s)` | Преобразует строку в `int`. |
| `shortValue()` | Преобразует в `short`. |
| `toString(int i)` | Преобразует `int` в строку. |
| `toString(double d)` | Преобразует `double` в строку. |
| `valueOf(String s)` | Преобразует строку в `Integer` или `Double`. |
| `valueOf(int i)` | Преобразует `int` в `Integer`. |
| `valueOf(double d)` | Преобразует `double` в `Double`. |

# <a name="class-integer-double"></a>🟠Классы для работы с Integer и Double

| Класс/Интерфейс | Описание |
|-----------------|----------|
| `Integer` | Обертка для примитивного типа `int`. Предоставляет методы для преобразования, сравнения и выполнения операций с целыми числами. |
| `Double` | Обертка для примитивного типа `double`. Предоставляет методы для работы с числами с плавающей точкой. |
| `Number` | Абстрактный класс, являющийся суперклассом для всех классов оберток числовых примитивных типов (`Integer`, `Double`, `Float`, `Long`, `Short`, `Byte`). |
| `BigInteger` | Класс для представления произвольно больших целых чисел. Поддерживает арифметические операции без ограничений на размер числа. |
| `BigDecimal` | Класс для представления чисел с плавающей точкой с произвольной точностью. Используется для финансовых и точных вычислений. |
| `Math` | Класс, предоставляющий статические методы для математических операций, таких как округление, возведение в степень, вычисление корней и тригонометрические функции. |
| `StrictMath` | Аналогичен классу `Math`, но гарантирует строгую портируемость результатов между разными платформами. |
| `AtomicInteger` | Класс для работы с целыми числами в многопоточной среде. Предоставляет атомарные операции (например, инкремент, декремент). |
| `AtomicLong` | Класс для работы с длинными целыми числами в многопоточной среде. Предоставляет атомарные операции. |
| `DoubleSummaryStatistics` | Класс для сбора статистики по набору чисел с плавающей точкой (например, минимум, максимум, среднее значение). |
| `IntSummaryStatistics` | Класс для сбора статистики по набору целых чисел. |
| `PrimitiveIterator.OfInt` | Интерфейс для итераторов, возвращающих значения типа `int`. |
| `PrimitiveIterator.OfDouble` | Интерфейс для итераторов, возвращающих значения типа `double`. |
| `IntStream` | Поток целых чисел (`int`), предоставляемый пакетом `java.util.stream`. |
| `DoubleStream` | Поток чисел с плавающей точкой (`double`), предоставляемый пакетом `java.util.stream`. |
| `Collectors` | Класс, предоставляющий методы для сбора результатов потоков, включая числовые операции (например, суммирование, усреднение). |
| `BitSet` | Класс для работы с наборами битов, который может использоваться для представления целых чисел или множеств. |

---
