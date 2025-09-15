
2025-02-16  14:35

Status: #child

Tags: #typescript

# Pizza App

```typescript
const menu = [
	{name: "Margherita", price: 8},
	{name: "Pepperoni", price: 10},
	{name: "Hawaiian", price: 10},
	{name: "Veggie", price: 9},
]

const globalId = 0
const cashInRegister = 100
const orderQueue = []

function addNewPizza(pizzaObj) {
	menu.push(pizzaObj)
}

function placeOrder(pizzaName) {
	for (var i = 0; i < menu.length; ++i) {
		const currentPizza = menu[i]
		if (pizzaName == currentPizza.name) {
			cashInRegister += currentPizza.price
			const orderQueueObj = {
			pizza: currentPizza.name,
			status: "ordered",
			id: globalId,
			}
			orderQueue.push(orderQueueObj)
			globalId++
			return orderQueueObj
		}
	}
	 
}

function completeOrder(orderId) {
	const selectedPizza = menu.find()
}
```


## References

