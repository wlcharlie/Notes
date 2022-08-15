---
title: In Operator & Instanceof
date: 2022-08-15
tags:
  - typescript
  - notes
---

#### In

```ts
type Fish = { swim: () => void };
type Bird = { fly: () => void };

function move(animal: Fish | Bird) {
	if ("swim" in animal) {
		return animal.swim();
	}

	return animal.fly();
}
```

#### Instanceof (Pure JS)

```ts
class Car {
  drive() {
    console.log("Driving...")
  }
}

class Truck {
  drive() {
    console.log("Driving a truck...")
  }

  loadCargo(amount: number) {
    console.log(`Loading cargo... ${amount}`)
  }
}

type Vehicle = Car | Truck

const v1 = new Car()
const v2 = new Truck()

function useVehicle(vehicle: Vehicle) {
  vehicle.drive()
  if ("loadCargo" in vehicle) {
    vehicle.loadCargo(1000)
  }
}

//or!

function useVehicle(vehicle: Vehicle) {
  vehicle.drive()
  if (vehicle instanceof Truck) {
    vehicle.loadCargo(1000)
  }
}
```