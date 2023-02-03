# Тип данных List (список)
#### `Список (List)` - это изменяемая структура данных, которая содержит упорядоченную последовательность элементов.
- Элементами списка могут быть объекты любого типа данных.
- Упорядоченость списков, подразумевает что элементы храняться в той последовательности в которой были добавлены.
- Элементы списка индексированы, то есть имеют свой порядковый номер. Индексация позволяет получить доступ к конкретному элементу списка, а так же к определенному диапазону элементов с помощю среза. Индексация начинается с нуля, а при попытке обращения к несуществующему индексу, возникает исключение `IndexError`. В случае со срезом, несуществующий индекс не вызовет исключение.
```
--- Пример упорядоченности списков ---

some_list = [1, 1.0, 1+1j, 'str', b'str', (1, 2), [1, 2], bytearray(b'array'), {1: 2}, {1,2}, frozenset([1,2]), True, None]

for element in some_list:
    print(type(element), element)

# <class 'int'>        1
# <class 'float'>      1.0
# <class 'complex'>    (1+1j)
# <class 'str'>        str
# <class 'bytes'>      b'str'
# <class 'tuple'>      (1, 2)
# <class 'list'>       [1, 2]
# <class 'bytearray'>  bytearray(b'array')
# <class 'dict'>       {1: 2}
# <class 'set'>        {1, 2}
# <class 'frozenset'>  frozenset({1, 2})
# <class 'bool'>       True
# <class 'NoneType'>   None

--- Пример доступа к элементу списка ---

print(some_list[0])   # 1
print(some_list[6])   # [1, 2]
print(some_list[12])  # None
print(some_list[-13]) # 1
print(some_list[13])  # IndexError: list index out of range

--- Пример среза ---

print(some_list[:])    # [1, 1.0, (1+1j), 'str', b'str', (1, 2), [1, 2], bytearray(b'array'), {1: 2}, {1, 2}, frozenset({1, 2}), True, None]
# поверхностная копия исходного списка

print(some_list[6:])   # [[1, 2], bytearray(b'array'), {1: 2}, {1, 2}, frozenset({1, 2}), True, None]
# начиная с 6-го индекса (включая его), до последнего

print(some_list[:6])   # [1, 1.0, (1+1j), 'str', b'str', (1, 2)]
# с начала, до 6-го индекса (НЕ включая его)

print(some_list[::6])  # [1, [1, 2], None]
# каждый 4-й элемент, начиная с первого

print(some_list[-6:])  # [bytearray(b'array'), {1: 2}, {1, 2}, frozenset({1, 2}), True, None]
# начиная с 6-го элемента (с конца) включая его, до последнего

print(some_list[:-6])  # [1, 1.0, (1+1j), 'str', b'str', (1, 2), [1, 2], bytearray(b'array'), {1: 2}, {1, 2}, frozenset({1, 2}), True]
# с начала, до 6-го элемента с конца (НЕ включая его)

print(some_list[::-4]) # [None, {1: 2}, b'str', 1]

```
