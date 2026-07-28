# REACT-notes-button_useState

## button to add numbers
- create button element with `onClick` inside `<button onClick={}> CickMe</button>`
- create a variable to define where to begin example (count) `let count = 0` 
- create a variable to be handle the function `const handleClick = () => {}`
-  inside it add what the function when clicking

````
const App = () => {
  let count = 0
  const handleClick = () => {
    count ++
    console.log(count)
  }

return(
<>
<h3>{count} </h3>
<button onClick={handleClick}> Cick me</button>
</>
)}
````

### (useState) for button to add numbers
#### now to make the count show in page 
- first import the useState `import { useState } from 'react'`
- now rewrite the above code to usestate
- the raw ` const [varible, setter function] = useState()` for count ` const [count, setCount] = useState(0)`
- now update the `handleClick` to increase count by one (but remember use setter function) `const handleClick = () => {setCount(count+1)}`
````
 const App = () => {

  // let count --> current state
 const [count, setCount] = useState(0)

  const handleClick = () => {
    setCount(count+1)
    console.log(count)
  }

return(
<>
<h3>{count} </h3>
<button onClick={handleClick}> Cick me</button>
</>
)}
````
## butom for dark mode
- Declare State with Array Destructuring `const [isDarkMode, setIsDarkMode] = useState(false) `
- adjust the function to be Boolean inside (handleClick) ` const handelClicked = (clickedBtn) => {}`
````
 const [isDarkMode, setIsDarkMode] = useState(false) 
  const handelClicked = (clickedBtn) => {
    if (clickedBtn === 'dark'){
      setIsDarkMode(true)
    }else{
      setIsDarkMode(false)
    }}
````
