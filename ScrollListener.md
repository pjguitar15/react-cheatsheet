# Scroll Listener

### Code Example
```javascript
const scrollListener = () => {
  if (window.scrollY >= 250) {
    setNavbar(true)
  } else {
    setNavbar(false)
  }
}

window.addEventListener('scroll', scrollListener)
```
