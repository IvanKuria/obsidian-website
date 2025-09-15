
2025-04-16  07:43

Status: #adult 

Tags: #computer-science #expressjs 

# Post Requests

``` javascript
// Route to send users

app.post("/api/users", (req, res) => {

	console.log(req.body);
	
	const { body } = req;
	
	const newUser = {
	
		id: mockUsers[mockUsers.length - 1].id + 1,
		
		...body
	
	};
	
	mockUsers.push(newUser);
	
	return res.status(201).send(newUser);

})

```

### Explanation
- *note*: make use of ThunderClient or Postman to make such requests
- first de-structure the body from req in order to get the new information
- we then make a *newUser* obj that has the id field and then use the spreader operator to add all the other info from *body*
- push the *newUser* to the *mockUsers* and return the 201 status code and the *newUser*
	- i.e. this json is sent:
		- {
			  "username": "Ivan",
			  "displayName": "Ivan the Great"
		 }
- this is how the response may look like:
	- {
		  "id": 7,
		  "username": "Ivan",
		  "displayName": "Ivan the Great"
	 }

## References
[Anson](https://www.youtube.com/watch?v=nH9E25nkk3I&t=1917s)


