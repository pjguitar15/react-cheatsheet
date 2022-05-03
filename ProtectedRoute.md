### App.js
```javascript
import ProtectedRoute from './ProtectedRoute'

const App = () => {  
  return (
    <Router>
      <Routes>
        <Route path='/' element={<SignIn />} />
        <Route element={<ProtectedRoute />}>
          // these are the outlet components
          <Route path='/home' element={<Home />} />
          <Route path='/account' element={<Account />} />
        </Route>
      </Routes>      
    </Router>
  );
};
```

### ProtectedRoute.js
> Outlet allows nested routes
```javascript
import { Outlet } from 'react-router'

const useAuth = () => {
  const user = { loggedIn: false }
  return user && user.loggedIn
}

const ProtectedRoute = () => {
  const isAuth = useAuth()
  return isAuth ? <Outlet /> : <SignIn />
}
```

### Profile.js
> this can only be accessed by authorized user
```javascript
import { withRouter } from 'react-router-dom'
const Profile = () => {
  return <div>If you see this, it means you are authenticated.</div>;
};

export default withRouter(Profile)
```
