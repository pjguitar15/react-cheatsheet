### Sample code
```javascript
import { useRef } from 'react'

const services = useRef(null)
const blog = useRef(null)
const contact = useRef(null)

const scrollToSection = (elementRef) => {
  elementRef.current.scrollIntoView({ behavior: 'smooth' })
}

<li onClick={() => scrollToSection(services)}>Go to Services</li>

<div ref={services}>Services<div/>
```
