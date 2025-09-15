
2024-10-19  14:17

Status: #child

Tags: [[React]]

# Props

## PropTypes

- Allows us to add specific information to react components
- You add the specific details in the App.jsx file

## Default Props
- it's an extension of the proptypes and allows us to add default values in case you didn't add specific values

## App.jsx

```js
import Student from "./Students";

function App() {
  return(
    <>
      <Student name="Ivan" age={30} isStudent={true}/>
      <Student name="Patrick" age={42} isStudent={false}/>
      <Student name="Squidward" age={50} isStudent={false}/>
      <Student name="Sandy" age={27} isStudent={true}/>
      <Student name="Larry"/>
    </>
  );
}

export default App
```

## Student.jsx

### PropTypes and Default Props

```js
import PropTypes from "prop-types"

function Student(props){
    return(
        <div className="student">
            <p>Name: {props.name}</p>
            <p>Age: {props.age}</p>
            <p>Student: {props.isStudent ? "Yes": "No"}</p>
        </div>  
    );
}

// Proptypes 
Student.propTypes = {
    name: PropTypes.string,
    age: PropTypes.number,
    isStudent: PropTypes.bool,
}

// Default Props
Student.defaultProps = {
    name: "Guest",
    age: 0,
    isStudent: false
}

export default Student
```


## Result

![[Pasted image 20241019142625.png]]
## References
[Bro Code](https://www.youtube.com/watch?v=CgkZ7MvWUAA)
