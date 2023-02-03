# Тип данных List (список)
#### `Список (List)` - это изменяемая структура данных, которая содержит упорядоченную последовательность элементов.
- Элементами списка могут быть объекты любого типа данных.
- Упорядоченость списков, подразумевает что элементы храняться в той последовательности в которой были добавлены.
- Элементы списка индексированы. То есть имеют свой порядковый номер (индексация начинается с нуля), что позволяет получить доступ к элементу списка с помощю индекса, и извлечь определенный диапазона элементов с помощю среза.
```
--- Пример упорядочености списков ---

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
print(some_list[13])  # IndexError: list index out of range
```
