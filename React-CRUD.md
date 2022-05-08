### Create
```javascript
setList([...list, {item: 'hello'}])
```

### Delete
```javascript
const deleteTodo = (id) => {
    const updatedTodos = [...list].filter((todo) => todo.id !== id)
    setList(updatedTodos)
}
```

### Edit
```javascript

```
