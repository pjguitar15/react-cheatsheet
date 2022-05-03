### App.js
```javascript
import ProtectedRoute from './ProtectedRoute'
import Profile from './Profile'

const App = () => {
  const [isAuth, setIsAuth] = useState(false)

  return (
    <Router>
      <Routes>
        <Route path='/' element={<><button>Login</button><button>Logout</button></>} />
      </Routes>
      <ProtectedRoute path='/profile' element={<Profile />} isAuth={isAuth} />
    </Router>
  );
};
```

### ProtectedRoute.js
```javascript
  const ProtectedRoute = ({ isAuth: isAuth, component: Component, ...rest }) => {
    return <Route {...rest} render={(props) => {
      if (isAuth) {
        return <Component />
      } else {
        return <Redirect to={{pathname: '/', state: { from: props.location }}} />
      }
    }} />
  }
```


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
