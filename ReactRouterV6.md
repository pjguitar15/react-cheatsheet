### How to Install
```bash
npm install react-router-dom@6
````

### Importing and Setting up
```javascript
import { BrowserRouter as Router, Routes, Route } from 'react-router-dom'
const App = () => {
  return (
    <Router>
      <Routes>
        <Route path='/' element={<Home />} />
        <Route path='/about' element={<About />} />
        <Route path='/profile' element={<Profile />} />
      </Routes>
    </Router>
  )
}
````

### Error Page
```javascript
<Route path='*' element={<ErrorPage />} />
````

### Link
> this is used for navbars only
> to remove style, just use style={{ textDecoration: 'none' }}
```javascript
import { Link } from 'react-router-dom'
<Link to='/'>Home</Link>
<Link to='/about'>About</Link>
<Link to='/profile'>Profile</Link>
````

### useNavigate
> used if you want to add a button functionality that redirects to another page
> example: submit a form then goes to another page 
```javascript
import { useNavigate } from 'react-router-dom'
let navigate = useNavigate()
<button onClick={() => {navigate('/about')}}>Go to About</button>
````
### useParams
```javascript
<Route path='/profile/:username' element={<Profile />}></Route>

// Profile.js
import { useParams } from 'react-router-dom'
let { username } = useParams()
<div>This is {username}'s profile page</div>
````
