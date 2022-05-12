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
> This should be handled inside the todo item!
```javascript
const deleteTodo = () => {
    setData(data.filter(item => item.id !== selectedId))
}
```

### Update
> This should be handled inside the todo item!
```javascript
    setData(data.map(item => {
        if(item.id === data.id){
            return {
                ...item, completed: !item.completed // use return statement to change the value inside map
            }            
        }
        return item // only returns when the if condition didn't match
    }))    
```
