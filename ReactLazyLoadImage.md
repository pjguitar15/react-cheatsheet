# React Lazy Loading Image

### Installation
```bash
npm i --save react-lazy-load-image-component
```

### Import
```javascript
import { LazyLoadImage } from 'react-lazy-load-image-component';
```

### Simple code example
```javascript
<LazyLoadImage
  alt={image.alt}
  height={image.height}
  src={image.src} // use normal <img> attributes as props
  width={image.width} />
```

### You can change the effect
> blur, black-and-white, opacity
```javascript
 <LazyLoadImage
    alt={image.alt}
    effect="blur"
    src={image.src} />
);
```

# Source
https://www.npmjs.com/package/react-lazy-load-image-component
