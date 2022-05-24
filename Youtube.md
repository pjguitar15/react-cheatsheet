### Install react-player
```bash
npm install react-youtube
```

### Youtube links only to react-player
```javascript
import React from 'react'
import ReactPlayer from 'react-player/youtube'

// Only loads the YouTube player
<ReactPlayer url='https://www.youtube.com/watch?v=ysz5S6PUM-U' />
```

### How to use react-player
> for any video links
```javascript
import ReactPlayer from 'react-player'

// Render a YouTube video player
<ReactPlayer url='https://www.youtube.com/watch?v=ysz5S6PUM-U' />
```

### Lazy
> to lazy load the appropriate player for the url you pass in
```javascript
import React from 'react'
import ReactPlayer from 'react-player/lazy'

// Lazy load the YouTube player
<ReactPlayer url='https://www.youtube.com/watch?v=ysz5S6PUM-U' />
```

# Source
https://www.npmjs.com/package/react-player
