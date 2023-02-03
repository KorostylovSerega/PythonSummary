# Тип данных List (список)
#### `Список (List)` - это изменяемая структура данных, которая содержит упорядоченную последовательность элементов.
- Элементами списка могут быть объекты любого типа данных.
- Упорядоченость списков, подразумевает что элементы храняться в той последовательности в которой были добавлены.
- Элементы списка индексированы, то есть имеют свой порядковый номер. Индексация позволяет получить доступ к конкретному элементу списка, а так же к определенному диапазону элементов с помощю среза. Индексация начинается с нуля, а при попытке обращения к несуществующему индексу, возникает исключение `IndexError`. В случае со срезом, несуществующий индекс не вызовет исключение.
```python
--- Пример упорядоченности списков ---

some_list = [1, 1.0, 1+1j, 'str', b'str', (1,), [1], bytearray(b'str'), {1: 2}, {1}, frozenset([1]), True, None]

for element in some_list:
    print(type(element), element)

# <class 'int'>        1
# <class 'float'>      1.0
# <class 'complex'>    (1+1j)
# <class 'str'>        str
# <class 'bytes'>      b'str'
# <class 'tuple'>      (1,)
# <class 'list'>       [1]
# <class 'bytearray'>  bytearray(b'str')
# <class 'dict'>       {1: 2}
# <class 'set'>        {1}
# <class 'frozenset'>  frozenset({1})
# <class 'bool'>       True
# <class 'NoneType'>   None

--- Пример доступа к элементу списка ---

print(some_list[0])   # 1
print(some_list[6])   # [1]
print(some_list[12])  # None
print(some_list[-13]) # 1
print(some_list[13])  # IndexError: list index out of range

--- Пример среза ---

print(some_list[:])    # [1, 1.0, (1+1j), 'str', b'str', (1,), [1], bytearray(b'str'), {1: 2}, {1}, frozenset({1}), True, None]
# поверхностная копия исходного списка

print(some_list[6:])   # [[1], bytearray(b'str'), {1: 2}, {1}, frozenset({1}), True, None]
# начиная с 6-го ИНДЕКСА (включая его), до последнего

print(some_list[:6])   # [1, 1.0, (1+1j), 'str', b'str', (1,)]
# с начала, до 6-го ИНДЕКСА (НЕ включая его)

print(some_list[::6])  # [1, [1], None]
# каждый 6-й ЭЛЕМЕНТ, начиная с первого

print(some_list[-6:])  # [bytearray(b'str'), {1: 2}, {1}, frozenset({1}), True, None]
# начиная с 6-го ЭЛЕМЕНТА (с конца) включая его, до последнего

print(some_list[:-6])  # [1, 1.0, (1+1j), 'str', b'str', (1,), [1]]
# с начала, до 6-го ЭЛЕМЕНТА с конца (НЕ включая его)

print(some_list[::-6]) # [None, [1], 1]
# каждый 6-ой ЭЛЕМЕНТ с конца, начиная с последнего
```
## Методы списков
Класс `list` имеет 11 встроеных методов.
- ### [list].append(item)
Добавляет элемент в конец списка.
```python
some_list = [1, 2, 3]
some_list.append(4)
print(some_list)  # [1, 2, 3, 4]
```
- #### [list].extend([other_list])
Расширяет список, добавляя в конец элементы другого списка.
```python
some_list = [1, 2, 3]
some_list.extend([4, 5, 6])
print(some_list)  # [1, 2, 3, 4, 5, 6]
```
- #### [list].insert(index, item)
Вставляет элемент в список, по указаному индексу. Элементы следующие за ним смещаются вправо. Если указаный индекс не существует, элемент будет добавлен в конец списка. При указании отрицательного индекса, счет элементов начинается с конца списка.
```python
some_list = [1, 2, 3]
some_list.insert(1, 4)
print(some_list)  # [1, 4, 2, 3]

some_list.insert(10, 4)
print(some_list)  # [1, 4, 2, 3, 4]

some_list.insert(-10, 4)
print(some_list)  # [4, 1, 4, 2, 3, 4]
```
- #### [list].remove(item)
Удаляет первый элемент с указаным значением. Если значение отсутствует в списке, возникает исключение `ValueError`.
```python
some_list = ['s', 'o', 'm', 'e', '_', 'l', 'i', 's', 't']
some_list.remove('s')
print(some_list)       # ['o', 'm', 'e', '_', 'l', 'i', 's', 't']
some_list.remove('x')  # ValueError: list.remove(x): x not in list
```

[↩Назад](https://github.com/KorostylovSerega/PythonSummary/blob/main/Python.md#2-типы-данных-в-python)
