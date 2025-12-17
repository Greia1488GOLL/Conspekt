# LeetCode Math (1)

```python
class Solution:
    def canMakeArithmeticProgression(self, arr: List[int]) -> bool:
        arr = sorted(arr)   #сортировка исходного массива
        result = True   #результат выполнения функции = по умолчанию True
        arr_len = len(arr) #длинна массива arr
        diff = arr [0] - arr[1] #разница между первым и вторым элементом отсортированного списка
        diff2 = 0
        if arr_len == 2:
            result = True
            return result
        for i in range(1, arr_len):
            
            if i + 1 != arr_len:
                diff2 = arr[i] - arr[i + 1]
                print(diff2)
        
            if diff != diff2:
                result = False
                return result
        result = True 
        return result
```

Итак этот код помогает определить арифметическую прогрессию, где при привальном ответе а именно если последовательность чисел является арифметической прогрессией то программа выводит: True. В ином случае если последовательность чисел не является прогрессией программа выводит: False. 
Например: 
3, 5, 1 - является арифметической прогрессией 
1, 2, 4 - не является арифметической прогрессией


# LeetCode Math (2)

```python
class Solution:
    def pivotInteger(self, n: int) -> int:
        x = 2
        while True:
            if 1 + x == x + n:
                    print(x)
                    return x

                    x += 1 
                    n -= 1
```

