
2025-04-16  07:19

Status: #adult

Tags: #computer-science #expressjs 

# Query Params

``` js
const mockUsers = [
	{id: 1, username: "anson", displayName: "Anson"},
	
	{id: 2, username: "ivan", displayName: "Ivan"},
	
	{id: 3, username: "john", displayName: "John"},
]

...

// Route to get all users

app.get("/api/users", (req, res) => {

	console.log(req.query)
	
	const {
	
		query: { filter, value }
	
	} = req;
	
	if (filter && value) return res.send(
		mockUsers.filter((user) => user[filter].includes(value))
	);  
	
	// when filter or value is undefined
	return res.send(mockUsers);

});

```

### Explanation
- when using a get request, you can make certain types of requests.
	- i.e. the url may look like this: http://localhost:3000/api/users?filter=username&value=an
	- in this case after the question mark, you can "filters" to the url to get certain information
	- in this case, we are filtering by username and then more specifically the substring *an* 
	- the result is [
		- {"id":1,"username":"anson","displayName":"Anson"},{"id":2,"username":"ivan","displayName":"Ivan"}
		- ]
- I've also included other checks to make sure that a filter and value is entered, otherwise the server will just return all mock users
## References
[Anson](https://www.youtube.com/watch?v=nH9E25nkk3I&t=1917s)

