---
title: 未整理Type Usage - Aliases & Custom Types
tags:
  - typescript
  - notes
---

#### Aliases & Custom Types

```ts
type Combinable = number | string

function combine(input1: Combinable, input2: Combinable) {
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

```ts
type Combinable = 'as-number' | 'as-text'
function func(type: 'as-number' | 'as-text')
function func(type: Combinable)
```

```ts
type Person = {
	name: string
	age: number
	role: [number, string]
}

const person: Person = { 
	name: 'meow',
	age: 4,
	role: [2, 'author']
} 
```