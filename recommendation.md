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
  response = linear_search(..)

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

        data = read_from_file(PATH)
        # when
        # then
        self.assertEqual('foo'.upper(), 'FOO')

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
