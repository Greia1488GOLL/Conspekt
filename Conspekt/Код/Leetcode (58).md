#Leetcode
```typescript 
function lengthOfLastWord(s: string): number {
    //Индекс последнего пробела в строке
    s = s.trim()
    let lst_space: number = s.lastIndexOf(" ");

    //Последнее слова в строке s
    let lst_word: string = s.slice(lst_space + 1);
    console.log(lst_word)

    //Вернуть длину последнего слова
    return lst_word.length;

};
```
