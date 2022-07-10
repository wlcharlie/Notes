---
title: 未整理Unknown Type
date: 2022-06-19
tags:
  - typescript
  - notes
---

```ts
let userInput: unknown
let userName: string

userInput = 5
userInput = 'Max'
if(typeof userInput === 'string') {
	userName = userInput
}

userName = userInput //error
```