
2025-03-26  14:49

Status: #adult

Tags: #computer-science #expressjs #backend 

# Get Requests

## Index.mjs

``` js
import express from "express"

const app = express();

const PORT = process.env.PORT || 3000;

app.listen(PORT, () => {

	console.log(`Server running on port ${PORT}`);

});

app.get("/api/users", (req, res) => {

	res.send([
	
	{id: 1, username: "anson", displayName: "Anson"},
	
	{id: 2, username: "ivan", displayName: "Ivan"},
	
	{id: 3, username: "john", displayName: "John"},
	
		]);

});

app.get("/api/products", (req, res) => {

	res.send([{id: 123, name: "chicken breast", price: 109}])

})

app.get("/", (req, res) => {

	res.status(201).send("Hello World");

});

```



## References

