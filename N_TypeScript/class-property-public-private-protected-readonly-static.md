---
title: Class Property
date: 2022-07-10
tags:
  - typescript
  - notes
  - class
---

#### Class Modifiers
>[ref](https://www.typescriptlang.org/docs/handbook/2/classes.html#member-visibility)

Typescript can control certain method or property are accessible outside the class (or extened class), by adding one of the following as prefix.

##### Member Visibility
* public* (default)
* private
* protected

##### Other Modifiers
* static*
* readonly

>`public` is a default modifier, you don't really need to code it in.
>`static` is as same feature as in JavaScript 

---
#### Examples
* Regular Class
```ts
class User {
	public greet() {
		console.log("Hello")
	}
}

const Matt = new User()
Matt.greet() //Hello
```
* With private
```ts
class User {
	//name: string
	//can be ignored since is defined in constructor
	constructor(private name: string) {
		//this.name = name
		//prev line can be ignored since the param has defined
	}

	greet() {
		console.log(`Hello, I am ${this.name}`)
	}
}

const user = new User("Matt")
user.greet() //Hello, I am Matt
user.name //error! only access inside the class
```
* With protected (to access in sub-class but not outside the class)
```ts
class User {
	//name: string
	//can be ignored since is defined in constructor
	constructor(private name: string) {
		//this.name = name
		//prev line can be ignored since the param has defined
	}

	protected getName() {
		return this.name
	}
}

class Doctor extends User {
	constructor(name: string){
		super(name)
	}

	greet() {
		console.log(`Hello, I am ${this.getName()}`)
	}
}


const doctor = new Doctor('John')
doctor.greet() //Hello, I John
doctor.getName() //error!
```
* With readonly
```ts
class User {
	//name: string
	//can be ignored since is defined in constructor
	constructor(readonly name: string) {
		//this.name = name
		//prev line can be ignored since the param has defined
	}
	
	greet() {
		console.log(`Hello, I am ${this.name}`)
	}

	changeName() {
		this.name = 'something else' //error!
	}
	
}

const user = new User('Loy')
console.log(user.name) //Loy
user.name = "Kevin" //error!
```
