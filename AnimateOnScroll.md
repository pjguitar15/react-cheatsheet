### How to install
```bash
npm install aos
```

### Import
```javascript
import 'aos/dist/aos.css'
```

### How to use
```html
<div data-aos='fade-down' data-aos-duration='2000'></div>
<div data-aos='flip-down' data-aos-duration='2000'></div>
```

### Better use it like this
```javascript
useEffect(() => {
  Aos.init({ duration: 2000 })
}, [])
```
