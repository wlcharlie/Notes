---
title: Union
date: 2022-08-15
tags:
  - typescript
  - notes
---

#### Union

略

#### Discriminated Union
A type that specific with a properies to discrimate (distinguish) between types that were unioned

```ts
type Shape =
	| { kind: "circle"; radius: number }
	| { kind: "square"; x: number }
	| { kind: "triangle"; x: number; y: number };

function area(s: Shape) {
	if (s.kind === "circle") {
		return Math.PI * s.radius * s.radius;
	} else if (s.kind === "square") {
		return s.x * s.x;
	} else {
		return (s.x * s.y) / 2;
	}
}
```