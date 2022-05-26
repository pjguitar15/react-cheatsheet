# How to send http request using Axios

### Installing Axios
```bash
npm install axios --save
```

### Import to project
```javascript
import axios from 'axios'
```

### Get request using Axios example
```javascript
axios.get(`https://jsonplaceholder.typicode.com/users`)
.then(res => {
  const persons = res.data;
  this.setState({ persons });
})
```

### Post request using Axios
```javascript
axios.post(`https://jsonplaceholder.typicode.com/users`, { user })
.then(res => {
  console.log(res);
  console.log(res.data);
})
```

### Delete request
```javascript
axios.delete(`https://jsonplaceholder.typicode.com/users/${this.state.id}`)
.then(res => {
  console.log(res);
  console.log(res.data);
})
```

### Put request
```javascript
const res = await axios.put('/api/article/123', {
    title: 'Making PUT Requests with Axios',
    status: 'published'
});
```
