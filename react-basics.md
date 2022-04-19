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

# Stopped at 29:09
[React JS Crash Course](https://www.youtube.com/watch?v=w7ejDZ8SWv8&ab_channel=TraversyMedia)
