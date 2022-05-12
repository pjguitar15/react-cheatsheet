### Map
```javascript
data.map((item, index) => (
  <div key={index}>{item.something}</div>
))
```

### Map and Filter
```javascript
data.filter((item) => item.id === 'd685db0a-99ae').map((item, index) => (
  <div key={index}>{item.something}</div>
))
```

### Filter and Slice and map
```javascript
data.filter(item => item.type === 'featured')
.slice(0, 3)
.map((item, index) => {
  // actions here
})
```
