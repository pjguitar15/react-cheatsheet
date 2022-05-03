### Code Example
```javascript
const [navbar, setNavbar] = useState(false)

const changeNavbarBackground = () => {
  if ((location.pathname === '/' || location.pathname === '/about') && window.scrollY >= 300) {
    setNavbar(true)
  } else {
    setNavbar(false)
  }
}
<Navbar className={`${navbar ? 'bg-white' : 'bg-none'}`}>
```
