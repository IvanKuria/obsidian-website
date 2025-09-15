
2025-03-26  15:01

Status: #adult

Tags: #computer-science #backend #expressjs 

# Route Params

## Index.mjs


``` js
const mockUsers = [
	{id: 1, username: "anson", displayName: "Anson"},
	
	{id: 2, username: "ivan", displayName: "Ivan"},
	
	{id: 3, username: "john", displayName: "John"},
]

// Route to get a single user by id

app.get("/api/users/:id", (req, res) => {

	console.log(req.params);
	
	// the id is a string by default so this will convert it to an int
	const parsedId = parseInt(req.params.id); 
	
	// checks to see if the parsedId is a valid int
	if (isNaN(parsedId)) {
		return res.status(400).send({msg: "Bad Request. Invalid Id."});
	}
	
	const findUser = mockUsers.find((user) => user.id === parsedId);
	
	if (!findUser) {
		return res.sendStatus(404);
	}
	
	return res.send(findUser);

});
```

## Explanation

*req.params* - this is used to get all the parameters. In this case that would be the id.
*parseInt* - this is a method that will convert a variable to an integer, if it's not possible, it will return NaN.


## References
[Anson](https://www.youtube.com/watch?v=nH9E25nkk3I&t=15369s) 

