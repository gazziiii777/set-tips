# Методы множеств

+ Метод `.add()` - _добавления нового элемента в множество_ 
+ Метод `.remove()` - _удаляет элемент из множества с генерацией исключения (ошибки) в случае, если такого элемента нет_
+ Метод `.discard()` - _удаляет элемент из множества без генерации исключения (ошибки), если элемент отсутствует_
+ Метод `.pop` - _удаляет и возвращает случайный элемент из множества с генерацией исключения (ошибки) при попытке удаления из пустого множества_
+ Метод `.clear()` - _удаляет все элементы из множества_
# Операции над множествами
+ Объединение множеств: метод `.union()` - _то множество, состоящее из элементов, принадлежащих хотя бы одному из объединяемых множеств_
+ Пересечение множеств: метод `.intersection()` - _это множество, состоящее из элементов, принадлежащих одновременно каждому из пересекающихся множеств. Для этой операции существует метод `.intersection()`_
+ Разность множеств: метод `.difference()` - _это множество, в которое входят все элементы первого множества, не входящие во второе множество. Для этой операции существует метод `.difference()`_
+ Симметрическая разность: метод `.symmetric_difference()` - _это множество, включающее все элементы исходных множеств, не принадлежащие одновременно обоим исходным множествам. Для этой операции существует метод `.symmetric_difference()`_

# Методы множеств, изменяющие текущие множества
+ Метод `.update()` - _изменяет исходное множество по объединению._
+ Метод `.intersection_update()` - _изменяет исходное множество по пересечению._
+ Метод `.difference_update()` - _изменяет исходное множество по разности._
+ Метод `.symmetric_difference_update()` - _изменяет исходное множество по симметрической разности._ 

## Подмножества и надмножества
+ Метод `.issubset()` - _для определения, является ли одно из множеств подмножеством другого_ 
+ Метод `.issuperset()` - _для определения, является ли одно из множеств надмножеством другого_
+ Метод `.isdisjoint()` - _для определения отсутствия общих элементов в множествах_
## Метод `.add()`

Для добавления нового элемента в множество используется метод `.add()`.

Следующий программный код:

```python
numbers = {1, 1, 2, 3, 5, 8, 3}  # создаем множество

numbers.add(21)  # добавляем число 21 в множество
numbers.add(34)  # добавляем число 34 в множество

print(numbers)
```

выводит (порядок элементов может отличаться):

```python
{1, 2, 3, 34, 5, 8, 21}
```

Не забывайте, что порядок элементов при выводе множества абсолютно произвольный.

Обратите внимание, для использования метода `.add()` требуется предварительно созданное множество, при этом оно может быть пустым.

Следующий программный код:

```python
numbers = set()  # создаем пустое множество

numbers.add(1)
numbers.add(2)
numbers.add(3)
numbers.add(1)

print(numbers)
```

выводит (порядок элементов может отличаться):

```python
{1, 2, 3}
```

Если требуется внести несколько значений в множество, то можно воспользоваться циклом for.

Следующий программный код:

```python
numbers = set()  # создаем пустое множество

for i in range(10):
    numbers.add(i * i + 1)

print(numbers)
```

выводит (порядок элементов может отличаться):

```python
{1, 2, 65, 5, 37, 10, 17, 50, 82, 26}
```

## Метод `.remove()` (метод удаленя)

Метод `.remove()` удаляет элемент из множества с генерацией исключения (ошибки) в случае, если такого элемента нет.

Следующий программный код:

```python
numbers = {1, 2, 3, 4, 5}

numbers.remove(3)
print(numbers)
```

выводит (порядок элементов может отличаться):

```python
{1, 2, 4, 5}
```

Следующий программный код:
```python
numbers = {1, 2, 3, 4, 5}

numbers.remove(10)
print(numbers)
```

приводит к возникновению ошибки `KeyError`, так как элемент `10` отсутствует в множестве.

## Метод `.discard()`

Метод `.discard()` удаляет элемент из множества без генерации исключения (ошибки), если элемент отсутствует.

Следующий программный код:

```python
numbers = {1, 2, 3, 4, 5}

numbers.discard(3)
print(numbers)
```

выводит (порядок элементов может отличаться):
```python
{1, 2, 4, 5}
```

Следующий программный код:

```python
numbers = {1, 2, 3, 4, 5}

numbers.discard(10)
print(numbers)
```

не приводит к возникновению ошибки и выводит (порядок элементов может отличаться):

```python
{1, 2, 3, 4, 5}
```

## Метод `.pop()`

Метод `.pop()` удаляет и возвращает случайный элемент из множества с генерацией исключения (ошибки) при попытке удаления из пустого множества.

Рассмотрим программный код:
```python
numbers = {1, 2, 3, 4, 5}

print('до удаления:', numbers)

num = numbers.pop()                 # удаляет случайный элемент множества, возвращая его

print('удалённый элемент:', num)

print('после удаления:', numbers)
```
Результат работы такого кода случаен, например, такой код может вывести:

```python
до удаления: {1, 2, 3, 4, 5}
удалённый элемент: 1
после удаления: {2, 3, 4, 5}
```

## Метод `.clear()`

Метод `.clear()` удаляет все элементы из множества.

Следующий программный код:
```python
numbers = {1, 2, 3, 4, 5}
numbers.clear()

print(numbers)
```
выведет:
```python
set()
```

# Операции над множествами
Основные операции над множествами:

+ объединение множеств; 
+ пересечение множеств; 
+ разность множеств;
+ симметрическая разность множеств.

Для каждой операции есть метод и оператор.
## Объединение множеств: метод `.union()`

__Объединение множеств__ – это множество, состоящее из элементов, принадлежащих хотя бы одному из объединяемых множеств. Для этой операции существует метод `.union()`.

![Иллюстрация к проекту](/images/union.png)
Приведенный ниже код:
```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset3 = myset1.union(myset2)
print(myset3)
```

выводит (порядок элементов может отличаться):
```python
{1, 2, 3, 4, 5, 6, 7, 8}
```
### Важно 

​Обратите внимание, метод `.union()` возвращает новое множество в которое входят все элементы множеств `myset1` и `myset2`. Для изменения текущего множества используется метод `.update()`.

Для объединения двух множеств можно также использовать оператор `|`.

Результат выполнения приведенного ниже кода:

```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset3 = myset1 | myset2
print(myset3)
```
аналогичен предыдущему.

## Пересечение множеств: метод `.intersection()`

__Пересечение множеств__ – это множество, состоящее из элементов, принадлежащих одновременно каждому из пересекающихся множеств. Для этой операции существует метод `.intersection()`.

![Иллюстрация к проекту](/images/intersection.png)

Приведенный ниже код:

```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset3 = myset1.intersection(myset2)
print(myset3)
```

выводит (порядок элементов может отличаться):

```python
{3, 4}
```
### Важно

​Обратите внимание, метод `.intersection()` возвращает новое множество в которое входят общие элементы множеств `myset1` и `myset2`. Для изменения текущего множества используется метод `.intersection_update()`.

Для пересечения двух множеств можно также использовать оператор `&`.

Результат выполнения приведенного ниже кода:

```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset3 = myset1 & myset2
print(myset3)
```

аналогичен предыдущему.

## Разность множеств: метод `.difference()`

__Разность множеств__ – это множество, в которое входят все элементы первого множества, не входящие во второе множество. Для этой операции существует метод `.difference()`.

![Иллюстрация к проекту](/images/difference.png)

Приведенный ниже код:

```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset3 = myset1.difference(myset2)
print(myset3)
```
выводит (порядок элементов может отличаться):

```python
{1, 2, 5}
```

Для разности двух множеств можно также использовать оператор `-`.

Результат выполнения приведенного ниже кода:

```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset3 = myset1 - myset2
print(myset3)
```

аналогичен предыдущему.

Обратите внимание: для операции разности множеств важен порядок, в котором указаны множества. Если поменять местами `myset1` и `myset2`, нас ожидает совсем другой результат: элементы, входящие в множество `myset2` и которых нет в множестве `myset1`.

Приведенный ниже код:

```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset3 = myset2.difference(myset1)
print(myset3)
```

выводит (порядок элементов может отличаться):

```python
{8, 6, 7}
```

## Симметрическая разность: метод `.symmetric_difference()`

__Симметрическая разность множеств__ – это множество, включающее все элементы исходных множеств, не принадлежащие одновременно обоим исходным множествам. Для этой операции существует метод `.symmetric_difference()`.


![Иллюстрация к проекту](/images//symmetric_defference.png)

Приведенный ниже код:

```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset3 = myset1.symmetric_difference(myset2)
print(myset3)
```

выводит (порядок элементов может отличаться):

```python
{1, 2, 5, 6, 7, 8}
```

Для симметрической разности двух множеств можно также использовать оператор `^`.

Результат выполнения приведенного ниже кода:
```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset3 = myset1 ^ myset2
print(myset3)
```
аналогичен предыдущему.

### Важно

​Обратите внимание: для операции симметрической разности порядок множеств не важен, на то она и симметрическая: `myset1 ^ myset2 == myset2 ^ myset1`

# Методы множеств, изменяющие текущие множества

## Метод `.update()`

Метод `.update()` изменяет исходное множество __по объединению__.

Приведенный ниже код:
```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset1.update(myset2)  # изменяем множество myset1
print(myset1)
```

выводит (порядок элементов может отличаться):
```python
{1, 2, 3, 4, 5, 6, 7, 8}
```

Аналогичный результат получается, если использовать оператор `|=`:
```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset1 |= myset2
print(myset1)
```

## Метод `.intersection_update()`
Метод `.intersection_update()` изменяет исходное множество __по пересечению__.

Приведенный ниже код:

```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset1.intersection_update(myset2)  # изменяем множество myset1
print(myset1)
```

выводит (порядок элементов может отличаться):

```python
{3, 4}
```

Аналогичный результат получается, если использовать оператор `&=`:

```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset1 &= myset2
print(myset1)
```

## Метод `.difference_update()`

Метод `.difference_update()` изменяет исходное множество __по разности__.

Приведенный ниже код:

```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset1.difference_update(myset2)  # изменяем множество myset1
print(myset1)
```

выводит (порядок элементов может отличаться):

```python
{1, 2, 5}
```

{1, 2, 5}

Аналогичный результат получается, если использовать оператор `-=`:

```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset1 -= myset2
print(myset1)
```

## Метод `.symmetric_difference_update()`

Метод `.symmetric_difference_update()` изменяет исходное множество __по симметрической разности__.

Приведенный ниже код:

```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset1.symmetric_difference_update(myset2)  # изменяем множество myset1
print(myset1)
```

выводит (порядок элементов может отличаться):
```python
{1, 2, 5, 6, 7, 8}
```

Аналогичный результат получается, если использовать оператор `^=`:

```python
myset1 = {1, 2, 3, 4, 5}
myset2 = {3, 4, 6, 7, 8}

myset1 ^= myset2
print(myset1)
```

# Подмножества и надмножества

Напомним, что множество `set1` является подмножеством множества `set2`, если все элементы первого входят во второе. При этом множество `set2` – надмножество множества `set1`.

## Метод `.issubset()`
Для определения, является ли одно из множеств подмножеством другого, используется метод `.issubset()`. Данный метод возвращает значение `True`, если одно множество является подмножеством другого, и `False`, если не является.

Приведенный ниже код:

```python
set1 = {2, 3}
set2 = {1, 2, 3, 4, 5, 6}

print(set1.issubset(set2))
```

выводит:

```python
True
```

В этом примере `set2` содержит все элементы `set1`. Это означает, что `set1` – подмно­жество `set2`. Это также означает, что `set2` – надмножество `set1`.

Для определения, является ли одно из множеств подмножеством другого, также применяются операторы `<=` (нестрогое подмножество) и `<` (строгое подмножество).

Приведенный ниже код:
```python
set1 = {2, 3}
set2 = {1, 2, 3, 4, 5, 6}

print(set1 <= set2)
```

аналогичен предыдущему.

## Метод `.issuperset()`

Для определения, является ли одно из множеств надмножеством другого, используется метод `.issuperset()`. Данный метод возвращает значение `True`, если одно множество является надмножеством другого, в противном случае он возвращает `False`.

Для определения, является ли одно из множеств надмножеством другого, используется метод `.issuperset()`. Данный метод возвращает значение `True`, если одно множество является надмножеством другого, в противном случае он возвращает `False`.

Приведенный ниже код:
```python
set1 = {'a', 'b', 'c', 'd', 'e'}
set2 = {'c', 'e'}

print(set1.issuperset(set2))
```

выводит:

```python
True
```

В этом примере `set1` содержит все элементы `set2`. Это означает, что `set1` – надмно­жество `set2`. Это также означает, что `set2` – подмножество `set1`.

Для определения, является ли одно из множеств надмножеством другого, также применяются операторы `>=` (нестрогое надмножество) и `>` (строгое надмножество).

Приведенный ниже код:

```python
set1 = {'a', 'b', 'c', 'd', 'e'}
set2 = {'c', 'e'}

print(set1 >= set2)
```

аналогичен предыдущему.

## Метод `.isdisjoint()`

Для определения отсутствия общих элементов в множествах используется метод `.isdisjoint()`. Данный метод возвращает значение `True`, если множества не имеют общих элементов, и  `False`, когда множества имеют общие элементы.

Приведенный ниже код:

```python
set1 = {1, 2, 3, 4, 5}
set2 = {5, 6, 7}
set3 = {7, 8, 9}

print(set1.isdisjoint(set2))
print(set1.isdisjoint(set3))
print(set2.isdisjoint(set3))
```

выводит:

```python
False
True
False
```