---
title: "Conditional Rendering"
type: tutorial
technology: react
date: 2024-10-19
maturity: seed
tags:
  - tutorial
  - web-dev
---

# Conditional Rendering
- allows you to control what gets rendered in your application based on certain conditions(show hide, or change components)
- in this case 

## App.jsx

```js
import UserGreeting from "./UserGreeting.jsx";

function App() {
  return(
    <>
      <UserGreeting isLoggedIn={true}/>
    </>
  );
}

export default App
```

## UserGreeting.jsx

### Conditional Props

```js
import PropTypes from "prop-types"

function UserGreeting(props){
    const welcomeMessage = <h2 className="welcome-message">
                           Welcome {props.userName}
                           </h2>
                           
    const loginPrompt =    <h2 className="login-prompt">
                           Please log in to continue
                           </h2>

    // Shorthand for if, else statement in JavaScript called ternary

    return(props.isLoggedIn ?  welcomeMessage: loginPrompt);

}

// Prop Types and Default Props
UserGreeting.proptypes = {
    isLoggedIn: PropTypes.bool,
    userName: PropTypes.string,
} 

UserGreeting.defaultProps = {
    isLoggedIn: false,
    userName: "Guest"
}

export default UserGreeting
```

## Index.css

```css
.welcome-message{
  font-size: 2.5em;
  background-color: lime;
  color: white;
  padding: 10px;
  border-radius: 5px;
  margin: 0;
}

.login-prompt{
  font-size: 2.5em;
  background-color: red;
  color: white;
  padding: 10px;
  border-radius: 5px;
  margin: 0;
}
```

## Results

### If logged in
![[react-conditional-rendering-logged-in.png]]

### If not logged in 
![[react-conditional-rendering-logged-out.png]]
## References
[Bro Code](https://www.youtube.com/watch?v=CgkZ7MvWUAA)
