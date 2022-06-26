---
title: Types - Object
date: 2022-06-26
tags:
  - typescript
  - notes
  - type
---
Object, you will see and use everyday type!

Example:
```typescript
const person = {
	name: 'Charlie',
	age: 26
}
```

Type infer by TypeScript:
![[Pasted image 20220626122108.png]]

* You can not access the key which is not existed:
	```typescript
	const person = {
		name: 'Charlie',
		age: 26
	}
	
	console.log(person.phone) //will throw error
	```
* You can add annotation: (not recommand approach)
	```typescript
	const person: object = {
		name: 'Charlie',
		age: 26
	}
	
	console.log(person.name) //will throw error: Property 'name' does not exist on type 'object'.
	```
* You can add annotation more specific: (good approach)
	```typescript
	const person: {
		name: string,
		age: number
	} = {
		name: 'Charlie',
		age: 26
	}

	```
	with type intellisense :D
	![[Pasted image 20220626123025.png]]
---
#### Interact with Functions
Example:
```typescript
function sum(a:number, b:number): number {
	return a + b
}

//or

//use ; or , either will do the work
function sum(numbers: { a:number; b: number }): number {
	return numbers.a + numbers.b
}
```

##### Optional Properties
Use `?` to infer a properies as optional
```typescript
function printName(obj: { first: string; last?: string }) {
	//...
}

// Both OK
printName({ first: "Bob" });
printName({ first: "Alice", last: "Alisson" });
```

When try using a propertie that may not exist:
```typescript
function printName(obj: { first: string; last?: string }) {
	// Error - might crash if 'obj.last' wasn't provided!
	console.log(obj.last.toUpperCase());
	
	//Object is possibly 'undefined'.Object is possibly 'undefined'.
	
	if (obj.last !== undefined) {
		// OK
		console.log(obj.last.toUpperCase());
	}
	
	// A safe alternative using modern JavaScript syntax:
	console.log(obj.last?.toUpperCase());
}
```