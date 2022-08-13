---
title: Singleton and Private Constructor Class
date: 2022-08-13
tags:
  - typescript
  - notes
  - class
---

#### Singleton Pattern in Class TypeScript
A pattern for some specific scenario that don't create more same class, which means the class can only create once.

##### Usage
* Private keyword: add private keyword on constructor
* Static method: since the constructor has private keyword, we can not no longer access with new. By using static method, we can access inside.
* Extra property: to store the instance that was created, to make sure we always use the same instance.

```ts
class Person {
    private static instance: Person

	private constructor () {
	  //...
	}

	static getInstance () {
	  //...
	  if (Person.instance) {
	    return this.instance
	  }

	  this.instance = new Person()
	}
}
```