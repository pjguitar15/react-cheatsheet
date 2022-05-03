### ProtectedRoute.js
```javascript
const ProtectedRoute = ({ user, children }) => {
  if (!user) {
    return <Navigate to="/landing" replace />;
  }

  return children;
};
```

### App.js
```javascript
const App = () => {
  ...

  return (
    <>
      ...

      <Routes>
        <Route index element={<Landing />} />
        <Route path="landing" element={<Landing />} />
        <Route
          path="home"
          element={
            <ProtectedRoute user={user}>
              <Home />
            </ProtectedRoute>
          }
        />
        ...
      </Routes>
    </>
  );
};
```

### Home.js
```javascript
const Home = () => {
  return <h2>Home (Protected: authenticated user required)</h2>;
};
```
