# Get Screen Size Value

### Sample Code
```javascript
const [windowDimension, detectHW] = useState({
  winWidth: window.innerWidth,
  winHeight: window.innerHeight,
})

const detectSize = () => {
  detectHW({
    winWidth: window.innerWidth,
    winHeight: window.innerHeight,
  })
}

useEffect(() => {
  window.addEventListener('resize', detectSize)

  return () => {
    window.removeEventListener('resize', detectSize)
  }
}, [windowDimension])
```

### Sample Usage
```javascript
const test = windowDimension.winWidth < 990 ? 'bg-black' : ''
```
