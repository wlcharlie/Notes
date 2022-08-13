---
title: Singleton and Private Constructor Class
date: 2022-08-13
tags:
  - typescript
  - notes
  - class
---

#### Singleton Pattern
A pattern for some specific scenario that don't create more same class, which means the class can only create once.

```ts
class Person {
	private constructor () {
	  //...
	}
}
```