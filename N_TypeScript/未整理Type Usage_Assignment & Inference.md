---
title: 未整理Type Usage - Assignment & inference
tags:
  - typescript
  - notes
---

>[!info]
>See [[2.Types]] 

#### Type Usage / Assignment and Inference

##### Basic (The Primitives: `string/number/boolean`)
1. You can specify a variable with semicolumn(annotaitions) `:`, like:
```ts
function add(num1: number, num2: number) {
	//...
}
```
2. Inference, as Typescript will generate type for you
```ts
const count = 5 //knowing the variabel as `number`, specific is 5 as `number`
const isGood = true //as `boolean`

let count = 5 //`number`
let word = 'hello'//`string`
```
3. You can assign type on variables
```ts
let count: number = null
```
4. DO NOT do this, which is redundant
```ts
// No type annotation needed -- 'count' inferred as type 'number'
const count: number = 5
```

---
##### with `object`

>[!example]
>```ts
>const person = {
>	name: 'meow',
>	age: 4
>}
>
>console.log(person)

^433fe0

1. you can not access the key that is not exsit (just like javascript but with error when development)
![[Pasted image 20220501230044.png]]
2. object type inferrred by ts
 ![[Pasted image 20220501230142.png]]
3. can do this but not enough full support 
	* not enough info about the content inside the object (see the error `person.name`)
	* no inteill (see [[未整理Type Usage_Assignment & Inference#^44ee70|next point (4.)]])
![[Pasted image 20220501230658.png]]
4. this is also same as [[#^433fe0|example]]
   ![[Pasted image 20220501232331.png]]

---
##### with `Array`
* using `[]` with prefix `string/number`, even `any`
* type can be flexible or strict (regarding the element types)
```ts
let activites: string[]
let activites: any[]
```

```ts

// hobbies: string[] 
const hobbies = ['Read', 'Music']

for(const hobby of hobbies) {
	console.log(hobby.toUpperCase())
}

```
---
##### Tuples
* added by typescript: fixed-length array
```ts
const person: {
	name: string
	age: number
	role: [number, string] //tuples!
} = { 
	name: 'meow',
	age: 4,
	role: [2, 'author']
} 

person.role.push('admin') //still work (a bug?)
person.role[1] = 10 //error!

person.role = [5, 'admin', 'user'] //will get a error
```
---
##### Enums

> This auto-incrementing behavior is useful for cases where we might not care about the member values themselves, but do care that each value is distinct from other values in the same enum. [Typescript Docs](https://www.typescriptlang.org/docs/handbook/enums.html)
* added by typescript: automatically enumerated global constant identifiers

>While string enums don’t have auto-incrementing behavior, string enums have the benefit that they “serialize” well.
```ts

//init ADMIN as 0, READ_ONLY as 1, AUTHOR as 2 (auto-incrementing)
enum Role { ADMIN, READ_ONLY, AUTHOR}

//init ADMIN as 5, READ_ONLY as 6, AUTHOR as 7 (auto-incrementing)
enum Role { ADMIN = 5, READ_ONLY, AUTHOR}

enum Role { ADMIN = 5, READ_ONLY = 3, AUTHOR} //author will be 2

//string, yes! but need to init all with string or number
//throw error at AUTHOR (without init a value)
enum Role { ADMIN = 5, READ_ONLY = "USER", AUTHOR} 

const person = { 
	name: 'meow',
	role: Role.ADMIN
} 
```
* how it looks in javascript
```js
var Role;
(function (Role) {
    Role[Role["ADMIN"] = 0] = "ADMIN";
    Role[Role["READ_ONLY"] = 1] = "READ_ONLY";
    Role[Role["AUTHOR"] = 2] = "AUTHOR";
})(Role || (Role = {}));

var person = {
    name: "meow",
    role: Role.AUTHOR
};
```
---
##### Any
* flexiable type
* but not really recommand (try to avoid)