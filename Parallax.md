### Install
```node
npm install react-parallax
```

### Import
```javascript
import { Parallax } from 'react-parallax'
```

### How to use
```javascript
import ImageFile from './file.jpg'

<Parallax className='image' bgImage={ImageFile} strength={800}>
  <div className='content'>
    Content goes here. Parallax height grows with content height.
  </div>
</Parallax>
```

### CSS
```css
.image {
  position: relative;
  height: 100vh;
}

.content {
  display: flex;
  align-items: center;
  justify-content: center;
  position: absolute;
  height: 100vh;
  width: 100%;
}
```
