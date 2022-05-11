### Create
```javascript
setList([...list, {item: 'hello'}])
```

### Read
```javascript
data.map((item, index) => (
    <div key={index}>{item.title}</div>
))
```

### Delete
```javascript
const deleteTodo = (id) => {
    const updatedTodos = [...list].filter((todo) => todo.id !== id)
    setList(updatedTodos)
}
```

### Update
```javascript

```
