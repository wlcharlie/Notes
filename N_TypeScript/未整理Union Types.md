---
title: 未整理Type Usage - Union Types
tags:
  - typescript
  - notes
---

#### Union Types

```ts
function combine(input1: number, input2: number) {
  const result = input1 + input2
  return result
}

const combinedAges = combine(30, 20)

const combinedNames = combine('Max', 'Anna') //error!
```

* to create a function that might accepts differ type, we can use union type

```ts
function combine(input1: number | string, input2: number | string) {
  let result
  if (typeof input1 === "number" && typeof input2 === "number") {
    result = input1 + input2
  } else {
    result = input1.toString() + input2.toString()
  }
  return result
}

const combinedAges = combine(30, 20)
const combinedNames = combine("Max", "Anna")
```

* `type User` see [[未整理Aliases & Custom Types]]
```ts
type User = { name: string } | string;
let u1: User = {name: 'Max'};
u1 = 'Michael';
```