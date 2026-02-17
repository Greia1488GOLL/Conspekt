```typescript
function addBinary(a: string, b: string): string {
    let result: number[] = [];
    let carry: number = 0;
    let i: number = a.length - 1;
    let j: number = b.length - 1;
    
    while (i >= 0 || j >= 0 || carry > 0) {
        const digitA: number = i >= 0 ? parseInt(a[i]) : 0;
        const digitB: number = j >= 0 ? parseInt(b[j]) : 0;
        
        const sum: number = digitA + digitB + carry;
        result.push(sum % 2);
        carry = Math.floor(sum / 2);
        
        i--;
        j--;
    }
    
    return result.reverse().join('');
}

```