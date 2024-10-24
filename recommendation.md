# Рекомендации по коду
Структура файла

```
# imports 

global PATH = '../txtf/input.txt'

def task1():
  data = read_from file(PATH)
  ...

if __name__ == 'main':
  task1()
```

Для тестов без unit

given-when-then - https://pythontest.com/strategy/given-when-then-2/

```

# imports 

global PATH = '../txtf/input.txt'


def should_linear_search__test():
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


Для unit test

should_"Что тест должен проверить"_test
```
import unittest

class TestStringMethods(unittest.TestCase):

    def should_linear_search__test(self):
        # given

        data = read_from_file(PATH)
        # when
        # then
        self.assertEqual('foo'.upper(), 'FOO')

if __name__ == '__main__':
    unittest.main()
```
