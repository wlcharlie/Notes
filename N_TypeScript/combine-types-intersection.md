---
title: Intersection
date: 2022-08-15
tags:
  - typescript
  - notes
---

#### Intersection
* Type (prefer)
```ts
type Admin = {
  name: string
  privileges: string[]
}

type Employee = {
  name: string
  startDate: Date
}


type ElevatedEmployee = Admin & Employee
```
* Interface
```ts
interface Admin {
  name: string
  privileges: string[]
}


interface Employee {
  name: string
  startDate: Date
}

interface ElevatedEmployee extends Admin, Employee {}
```

#### Union
* the symbol: `|`
```ts
type Combinable = string | number
type Numeric = number | boolean

type Universal = Combinable & Numeric
```