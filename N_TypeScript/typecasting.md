---
title: Type Casting
date: 2022-08-15
tags:
  - typescript
  - notes
---

```ts
const userInputElement = <HTMLInputElement>document.getElementById('#user-input')

//OR

const userInputElement = document.getElementById(
  "#user-input"
) as HTMLInputElement

  

userInputElement.value = "WOW?"
```