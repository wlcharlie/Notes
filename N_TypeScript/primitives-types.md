---
title: Types - The Primitives 
date: 2022/06/26
tags:
  - typescript
  - notes
---

JavaScript has three commonly used primitives: `string`, `number`, and `boolean`. There is also correspoding type in TypeScript. As known:
* `string` as `"Hello, world!"`
* `number` as `4`, `568` (same as in JavaScript, `number` is just number no matter is int/float/long)
* `boolean` as `true` or `false`

>[!info]
>Always use LOWER case of `string`, `number`, and `boolean`.
>Upper Case is ok, but in case of encountering some special built-in types, use LOWER case instead!

#### Ty

---
#### string type
```typescript
let sentence = "How are you"? //type inference as string by ts

let word: string //assign type
```
---
#### number type
```typescript
let count = 15

let totalAmount: number
```
---
#### boolean type
```typescript
let isCheck = false

let isDone: number
```