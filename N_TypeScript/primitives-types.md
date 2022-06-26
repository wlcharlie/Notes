---
title: Types - The Primitives 
date: 2022-06-26
tags:
  - typescript
  - notes
  - type
---

JavaScript has three commonly used primitives: `string`, `number`, and `boolean`. There is also correspoding type in TypeScript. As known:
* `string` as `"Hello, world!"`
* `number` as `4`, `568` (same as in JavaScript, `number` is just number no matter is int/float/long)
* `boolean` as `true` or `false`

>[!info]
>Always use LOWER case of `string`, `number`, and `boolean`.
>Upper Case is ok, but in case of encountering some special built-in types, use LOWER case instead!

#### Type annotation

Adding type after a variable, like:
```typescript
let name: string = 'Charlie'
```
Since TypeScript will infer the type automatically, we can take out the annotation:
```typescript
// No type annotation needed -- 'name' inferred as type 'string'
let name = 'Charlie'
`````

---
#### string type
```typescript
let sentence = "How are you"? //type infer as string by ts

let word: string //assign type
```
---
#### number type
```typescript
let count = 15

let totalAmount: number
```
---
#### boolean type
```typescript
let isCheck = false

let isDone: number
```
---
#### Interact with Function

##### Parameter Type Annotations
Just like normal type annotations, you can add it after parameter
```typescript
function greet(name: string) {
	console.log("Hello, " + name.toUpperCase() + "!!");
}

greet(42) //will throw an error during deveploment
```
![[Pasted image 20220626120349.png]]
##### Return Type Annotations
You can also infer the value that the function return, but also typescript will automatically check the type itself. You usaually don't need to annotate, but you may do it for documentation or personal preference(coding style)
```typescript
function getAge(): number {
  return 26
}
```
##### Anonymous Function
Example:
```typescript
// No type annotations here, but TypeScript can spot the bug

const names = ["Alice", "Bob", "Eve"];

// Contextual typing for function
names.forEach(function (s) {
	console.log(s.toUppercase());
	//Property 'toUppercase' does not exist on type 'string'. Did you mean 'toUpperCase'?
});

// Contextual typing also applies to arrow functions
names.forEach((s) => {
	console.log(s.toUppercase());
	//Property 'toUppercase' does not exist on type 'string'. Did you mean 'toUpperCase'?
});
```
Even though the parameter `s` didn’t have a type annotation, TypeScript used the types of the `forEach` function, along with the inferred type of the array, to determine the type `s` will have.

This process is called _contextual typing_ because the _context_ that the function occurred within informs what type it should have.