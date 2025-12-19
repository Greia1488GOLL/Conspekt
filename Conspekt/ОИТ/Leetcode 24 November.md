

```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next
```

```python
def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:
```
 Метод принимает два связных списка (`list1`, `list2`), каждый из которых может быть None (пустым).
Возвращает объединённый отсортированный список.

```python 
res = ListNode()  # создаём фиктивный узел
head = res        # head будет указывать на начало списка (фиктивный узел)
t = None          # t будет хранить предыдущий узел перед res
```
res сразу является фиктивным узлом, но без значения (val=0 по умолчанию).
head ссылается на этот узел, чтобы потом вернуть начало списка (`head`).
t будет использоваться, чтобы отслеживать предыдущий узел и удалить лишний пустой узел в конце

```python
while list1 and list2:
    if list1.val <= list2.val:
        res.val = list1.val
        list1 = list1.next
    else:    
        res.val = list2.val
        list2 = list2.next
    res.next = ListNode()
    t = res
    res = res.next
```

Сравниваем значения текущих узлов `list1` и `list2`.
Меньшее значение записываем в `res.val`.
Сдвигаем указатель того списка, чей элемент взяли.
Создаём новый пустой узел ListNode() и присоединяем его к res.next — это важно: мы заранее создаём следующий узел, даже если он может оказаться лишним (это приведёт к проблеме, которую мы исправим позже).
t запоминает текущий узел `res` (который только что заполнили).
Переходим к новому узлу `res = res.next`

```python

while list1:
    res.val = list1.val
    list1 = list1.next
    res.next = ListNode()
    t = res
    res = res.next
```

Если в `list1` остались элементы (а `list2` закончился), копируем их по одному.
Каждый раз создаём новый узел после текущего — та же логика, что и в первом цикле.

```python
while list2:
    res.val = list2.val
    list2 = list2.next
    res.next = ListNode()
    t = res
    res = res.next
```

Аналогично для оставшихся элементов  list2

```python
if t:
    t.next = None    
else:
    head = None
```

t всегда указывает на последний заполненный узел.
 После всех циклов `res` указывает на пустой узел (`ListNode()`), который был создан последним и не должен быть в итоговом списке.
Поэтому `t.next = None` отрезает этот лишний узел.
Если `t` равно `None` (это значит, что оба списка были пусты), то `head` (который указывает на изначальный фиктивный узел) должен стать `None`

```python
return head
```
Возвращаем указатель на начало списка