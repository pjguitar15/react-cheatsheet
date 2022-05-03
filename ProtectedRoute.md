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
import { Navigate, Outlet } from 'react-router'

const useAuth = () => {
  const user = { loggedIn: false }
  return user && user.loggedIn
}

const ProtectedRoute = () => {
  const isAuth = useAuth()
  return isAuth ? <Outlet /> : <Navigate to='/' />
}
```
