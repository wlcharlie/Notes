---
title: Abstract Classes
date: 2022-08-13
tags:
  - typescript
  - notes
  - class
---

#### Abstract Keyword
To enforce all related extened class share same method or properties, an abstract method or class can not implented or init itself.

* To enforce extened class must have certain method

```ts
class Person {
    //...
	abstract speak(this: Person): void
}

class Student extends Person {
	speak() {
	  //...
	}
}
```

* or add in front of the class
```ts
abstract class Person {
  //...
}

const Student = new Person //X
```