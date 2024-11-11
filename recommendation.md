# Рекомендации по коду
## Структура файла

```
# imports 

global PATH = '../txtf/input.txt'

def task1():
  data = read_from file(PATH)
  ...

if __name__ == 'main':
  task1()
```

## Для тестов без unit

given-when-then - https://pythontest.com/strategy/given-when-then-2/
test_should_"Что тест должен проверить"

```

# imports 

global PATH = '../txtf/input.txt'


def test_should_linear_search_():
  # given
  data = read_from_file(PATH)
   
  # when
  response = linear_search(data)

  # then
  if response == response:
    print("Равно")
  else 
    print("Не равно")



if __name__ == 'main':
  should_linear_search__test()

```


## Для unit test
given-when-then - https://pythontest.com/strategy/given-when-then-2/

test_should_"Что тест должен проверить"
```
import unittest

class TestStringMethods(unittest.TestCase):

    def test_should_linear_search(self):
        # given
        expected_result= "Что-то"
        data = read_from_file(PATH)

        # when
        result = linear_search(data)

        # then
        self.assertEqual(result, expected_result)

if __name__ == '__main__':
    unittest.main()
```

## Для работы с относительными путями в проектах на Python, важно понимать, как интерпретируются различные виды путей. Давайте рассмотрим несколько вариантов:

#### 1. Относительные пути в Python

Относительные пути в Python интерпретируются относительно текущего рабочего каталога (current working directory), который можно узнать с помощью функции os.getcwd().

Пример:
```
import os

# Получение текущего рабочего каталога
current_dir = os.getcwd()
print(f"Текущий рабочий каталог: {current_dir}")

# Использование относительного пути
relative_path = '../textsf/input.txt'
absolute_path = os.path.join(current_dir, relative_path)
print(f"Абсолютный путь: {absolute_path}")
```
#### 2. Использование __file__ для относительных путей

Если вы хотите использовать относительный путь относительно текущего скрипта, вы можете использовать __file__, чтобы получить путь к текущему скрипту, а затем построить относительный путь оттуда.

Пример:
```
import os

# Получение пути к текущему скрипту
current_script_dir = os.path.dirname(os.path.abspath(__file__))

# Использование относительного пути относительно текущего скрипта
relative_path = '../textsf/input.txt'
absolute_path = os.path.join(current_script_dir, relative_path)
print(f"Абсолютный путь: {absolute_path}")
```
#### 3. Использование . и .. для навигации по каталогам

Вы можете использовать . для текущего каталога и .. для родительского каталога для построения относительных путей.

Пример:

```
import os

# Получение пути к текущему скрипту
current_script_dir = os.path.dirname(os.path.abspath(__file__))

# Использование относительного пути относительно текущего скрипта
relative_path = os.path.join(current_script_dir, '..', 'textsf', 'input.txt')
absolute_path = os.path.abspath(relative_path)
print(f"Абсолютный путь: {absolute_path}")
```

## Запуск тестов и задний

Вам нужно сделать запуск тестов и заданий в одну копку.
Это необходимо сделать на уровне конкретной лабы и запуск всех лаб. 

Сделайте для этого нормальный вывод в консоль для того, чтобы было видно какая лаба/задача  запускается с каким входными ив выходными данными.

##  Проблама импрота `import *`
Импорт всех функций и классов из модуля с помощью from module import * может привести к нескольким проблемам, особенно в больших проектах. Вот некоторые из них:

1. Конфликты имен
   
Если в разных модулях есть функции или классы с одинаковыми именами, это может привести к конфликтам имен. Например, если у вас есть две функции read_data в разных модулях, импорт всех функций из обоих модулей может вызвать конфликт.

2. Трудности с отладкой

Когда вы импортируете все функции и классы из модуля, становится сложнее отследить, откуда именно была импортирована та или иная функция. Это может затруднить отладку и понимание кода.

3. Проблемы с поддержкой кода

Импорт всех функций и классов из модуля может сделать код менее читаемым и поддерживаемым. Другие разработчики, работающие с вашим кодом, могут не понять, откуда именно были импортированы те или иные функции и классы.

4. Проблемы с производительностью

Импорт всех функций и классов из модуля может привести к увеличению времени загрузки и использования памяти, особенно если модуль содержит много функций и классов.

### Рекомендации
Импортируйте только необходимые функции и классы:

```
from Utils.Read_n_Write import read_data, write_data
```
Используйте псевдонимы для модулей:

```
import Utils.Read_n_Write as rw
rw.read_data()
rw.write_data()
```
Используйте __all__ в модулях:
В модуле Utils.Read_n_Write вы можете определить, какие функции и классы должны быть доступны при использовании from module import *.

```
__all__ = ['read_data', 'write_data']
```
Избегайте использования from module import *:
Старайтесь избегать использования from module import * в больших проектах. Это поможет избежать конфликтов имен и улучшить читаемость и поддерживаемость кода.





