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
