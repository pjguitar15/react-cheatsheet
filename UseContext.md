### ContextProvider.js
> You can rename it like "AuthProvider.js" or "LoadingProvider.js"
```javascript
import React, { useContext } from 'react'
const AuthContext = React.createContext()
export const useAuth = () => {
  return useContext(AuthContext)
}

// don't forget the export!
export const ContextProvider = ({ children }) => {
  const test = 'This is a variable from useContext'
  const value = {
    test,
  }
  return <AuthContext.Provider value={value}>{children}</AuthContext.Provider>
}
```

### Import into App.js
```javascript
import { ContextProvider } from './ContextProvider';
function App() {
  return (
    <div className="App">
      <Router>
        {/* Inside this context provider, you can provide all the global variables needed */}
        <ContextProvider> 
          <Routes>
            <Route path='/' element={<LoginPage />} />            
          </Routes>
        </ContextProvider>
      </Router>
    </div>
  );
}

export default App;
```

### How to use
> just import useAuth, and now you can take any variable from there
```javascript
import { useAuth } from './AuthProvider'
const { test } = useAuth()
```
