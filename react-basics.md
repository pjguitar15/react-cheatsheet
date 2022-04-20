### Basic Boiler Plate
```javascript
export const Header = () => {
  return (
    <div>
      <h1>My Header</h1>
    </div>
  )
}
```

### Create React App
```bash
npx create-react-app my-app
cd my-app
npm start
```

### React Snippets
```
rafce // generates arrow function component
```

### Props
```javascript
<Header title='Hello' /> // from another component

const Header = (props) => {
  return(
    <div>
      <h1>{props.title}</h1>
    </div>
  )
}
```

### Input useState
```javascript
const [input, setInput] = useState('')
<input value={input} onChange={(e) => setInput(e.target.value)} className='form-control'
placeholder='Add todo item'/>
```

### Array useState
> using onClick attribute
``` javascript
const [todoItems, setTodoItems] = useState([])

// button handler
const buttonHandler = () => {
  if (input != '') {
    setTodoItems([...todoItems, input])
    console.log(todoItems)
    setInput('')
  }
}

<button onClick={buttonHandler} className='btn btn-sm btn-primary'>
Add </button>
```

### Map Function
> take note: parentheses and not curly brackets
```javascript
<ul className='list-group'>
  {todoItems.map((item, index) => (
    <li key={index} className='list-group-item'>
      {item}
    </li>
  ))}
</ul>
```

# Stopped at 29:09
[React JS Crash Course](https://www.youtube.com/watch?v=w7ejDZ8SWv8&ab_channel=TraversyMedia)
