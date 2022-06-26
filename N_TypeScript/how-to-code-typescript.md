---
title: How to code TypeScript
date: 2022/06/26
tags:
  - typescript
  - notes
---

#### How to code TypeScript
1. Creating file as `.ts`
2. Code as normal JavaScript, but with [[2.Types]]
3. Commad line: `tsc file.ts` to compile ts to JS

>TypeScript
```ts
function add(n1: number, n2: number, showResult: boolean, phrase: string) {
  const result = n1 + n2
  if (showResult) {
    console.log(phrase + result)
  } else {
    return n1 + n2
  }
}

const number1 = 5
const number2 = 30
const printResult = true
const resultPhrase = "Result is: "

add(number1, number2, printResult, resultPhrase)
```

> JavaScript
```js
function add(n1, n2, showResult, phrase) {
    var result = n1 + n2;
    if (showResult) {
        console.log(phrase + result);
    }
    else {
        return n1 + n2;
    }

}

var number1 = 5;
var number2 = 30;
var printResult = true;
var resultPhrase = "Result is: ";

add(number1, number2, printResult, resultPhrase);
```