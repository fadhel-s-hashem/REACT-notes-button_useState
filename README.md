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
- now rewrite the above code to useState (Array Destructuring )
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
- use a ternary for Boolean `{isDarkMode ? 'dark' : 'light'}`
- create a button with (onClick) `<button onClick={() => handelClicked('dark')}>`
````
const [isDarkMode, setIsDarkMode] = useState(false) 
  const handelClicked = (clickedBtn) => {
    if (clickedBtn === 'dark'){
      setIsDarkMode(true)
    }else{
      setIsDarkMode(false)

return(
<div className={isDarkMode ? 'dark' : 'light'}>
<button onClick={() => handelClicked('dark')}> Dark mode</button>
<button onClick={() => handelClicked('light')}> light mode</button>
</div>
)}
````

## button for Array
the tydent array `const initialState = ['Ali', 'zainab' , 'omar' , 'sayed' , 'zaid']`
- same as before add  Array Destructuring `const [students, setStudents] = useState(initialState)`
- use `.map` function to loop through the arrey `{students.map((student) => (() => {})`
---
- create handle function `const handleDelete = (clickedStudent)=>{}` to add in onClick
- inside add `.filter` function to delete `const result = students.filter((removeStudent =>` `removeStudent !== clickedStudent)`
- this part `removeStudent !== clickedStudent)` mean that clicked student will be filtered and won't keep in the new array `result`
- put `setStudents(result)` at the end to update the `student array`
 * how `handleDelete` look like
````
const handleDelete = (clickedStudent)=>{
    const result = students.filter((removeStudent) => removeStudent !== clickedStudent)
    setStudents(result)
}
 ````
- inside the `map`add buttom with onClick to delete ` <button onClick={}> delete student </button>`
- inside cnClick creat arrow function foe handleDelete `onClick={() => handleDelete (student)}`
- by adding the arrow function its like telling react dont delete all students just delete the clicked one
````
{students.map((student) => (
  <>
  <li> {student} </li>
  <button onClick={() => {handleDelete (student)}}> Delete {student}</button>
  </>
))}
````
---
### to show deleted students

