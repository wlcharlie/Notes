---
title: 未整理Function - Type, Return, Callback, Void
date: 2022-06-19
tags:
  - typescript
  - notes
---

#### Function Return Type
![[Pasted image 20220619111925.png]]
![[Pasted image 20220619112014.png]]

 ![[Pasted image 20220619112139.png]]
* the calculation is not same type as the inference
* let typescript do infer itself

---
#### White Type - Void
![[Pasted image 20220619112745.png]]

* Undefined is a valid type, also do not use it unless you have a specfic scanrio to do so
* if function has no return (in typescript)
```ts
function printResult(num: number): void {
  console.log("Result: " + num)
}

//wrong
function printResult(num: number): undefined {
  console.log("Result: " + num)
}

//correct
function printResult(num: number): undefined {
  console.log("Result: " + num)
  return
}

//this is also not wrong
function printResult(num: number): void {
  console.log("Result: " + num)
  return
}
```
---
#### Function as Type

Function is a type in typescript
![[Pasted image 20220619113810.png]]

to be more presice on spcefic function
![[Pasted image 20220619114054.png]]