---
title: Interface
date: 2022-08-13
tags:
  - typescript
  - notes
---

#### Interface
Same as `type` to create a custom type.

```ts
interface Person {
  name: string
  age: number
  greet(phrase: string): void

}

let user1: Person

user1 = {
  name: "MAX",
  age: 25,

  greet(phrase: string) {
    console.log(phrase + " " + this.name)
  },
}
```

#### Difference with Custom Types
* Interface only descride how object like, and only to define object.
* good to use on Class, to implements how Class should like.

```ts
interface Greetable {
  name: string
  greet(phrase: string): void
}

  
class Person implements Greetable {
  name: string
  age = 30  //is ok!
  constructor(n: string) {
    this.name = n
  }

  greet(phrase: string): void {
    console.log(phrase + " " + this.name)
  }

}

let user1: Greetable

user1 = new Person("Max")

user1.greet("Hi there - I am")
```

##### Readonly Modifier
can use on `interface` or `type`
```ts
interface Greetable {
  readonly name: string
  greet(phrase: string): void
}

//...

user1.name = "Kevin" //X
```

#### Extending Interface
To seperate logic and structure, but meanwhile you can merge together by extending
```ts
interface Named {
  readonly name: string
}

interface Greetable extends Named {
  greet(phrase: string): void
}
```

##### Interface as Function 
```ts
interface AddFn {
  (a: number, b: number): number
}

  

let add: AddFn = (a: number, b: number) => {
  return a + b
}
```

##### Optional Properties
Just add  `?`
```ts
interface Named {
  readonly name: string
  age?: number
}
```