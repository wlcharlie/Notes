---
title: 未整理Never Type
date: 2022-06-19
tags:
  - typescript
  - notes
---
a type never intend to return anything, since it crash
```ts
let userInput: unknown
let userName: string

userInput = 5
userInput = 'Max'
if(typeof userInput === 'string') {
	userName = userInput
}

function generateError(message: string, code: number): never {
	throw { message: message, errorCode: code }
}
```
