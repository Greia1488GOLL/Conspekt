#Leetcode
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
```Python
class Solution:
    def pivotInteger(self, n: int) -> int:
        total_sum = n * (n + 1) // 2
        
        for x in range(1, n + 1):
            left_sum = x * (x + 1) // 2
            right_sum = total_sum - left_sum + x
            
            if left_sum == right_sum:
                return x
        
        return -1
```

<<<<<<< HEAD:Conspekt/Код/LeetCode Math (1).md
Алгоритм проверяет каждое возможное число от 1 до n как кандидата на роль опорного числа. Для каждого кандидата вычисляются суммы левой и правой частей, затем они сравниваются.
1. **Вычисляем общую сумму** всех чисел от 1 до `n` по формуле:  
total_sum = n × (n + 1) ÷ 2
2. **Перебираем все числа** от 1 до n:
Для текущего числа x считаем сумму левой части: left_sum = x × (x + 1) ÷ 2
Вычисляем сумму правой части: right_sum = total_sum - left_sum + x
3. **Сравниваем суммы**:
Если left_sum == right_sum — мы нашли опорное число!
Если не равны — переходим к следующему кандидату
4. **Возвращаем результат**:
Если нашли подходящее x — возвращаем его
Если ни одно число не подошло — возвращаем -1


# LeetCode Math (3)
```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        if x < 0:
            return False
        
        original = x
        reversed_num = 0
        
        while x > 0:
            digit = x % 10 
            reversed_num = reversed_num * 10 + digit
            x //= 10
        
        return original == reversed_num
```

1. **Проверяем отрицательные** — если число < 0, сразу False
2. **Сохраняем исходное** — запоминаем число для сравнения
3. **Переворачиваем число** — в цикле берём последнюю цифру, добавляем к перевёрнутому, удаляем из исходного
4. **Сравниваем** — если исходное = перевёрнутому, то True, иначе False
5. **Работает для всех случаев** — 0 и однозначные = палиндромы, числа с 0 на конце ≠ палиндромы


# LeetCode Math (4)
```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        if x < 0:
            return False
        
        rev = 0
        temp = x
        
        while temp > 0:
            rev = rev * 10 + temp % 10
            temp //= 10
            
        return x == rev
```

1. **Проверка отрицательных чисел**  
Если число < 0 → сразу False (отрицательные не палиндромы)
2. **Копирование числа**  
Сохраняем исходное число в переменной temp для обработки
3. **Создание перевернутого числа**  
Инициализируем rev = 0 (здесь будет результат)
4. **Цикл переворота:**  
Пока temp > 0:
- Берем последнюю цифру: temp % 10
- Добавляем к `rev`: rev = rev * 10 + цифра
- Убираем последнюю цифру: temp //= 10
5. **Сравнение**  
Сравниваем исходное число x с перевернутым rev  
Равны → True, не равны → False
=======
                    x += 1 
                    n -= 1
```

>>>>>>> 40891b3f722fdac3dd06225309b1c7b88cb602c9:Conspekt/Код/LeetCode Math.md
