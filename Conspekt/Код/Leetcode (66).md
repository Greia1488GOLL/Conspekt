```typescript
function plusOne(digits: number[]): number[] {
    for (let i = digits.length - 1; i >= 0; i--) {
        if (digits[i] < 9) {
            digits[i] += 1;
            return digits;
        }
        digits[i] = 0;
    }
    
    // Если все цифры были 9, добавляем 1 в начало
    return [1, ...digits];
}
```
