### Install react-youtube
```bash
npm install react-youtube
```

### Install get-youtube-id
```bash
npm install get-youtube-id
```

### How to use get-youtube-id
```javascript
var getYouTubeID = require('get-youtube-id');
 
var id = getYouTubeID("http://www.youtube.com/watch?v=9bZkp7q19f0");
console.log(id); // "9bZkp7q19f0"
 
 
// Or, if you're using ES6 syntax:
import getYouTubeID from 'get-youtube-id';
```

### How to use react-youtube
```javascript
import React from 'react';
import YouTube from 'react-youtube';

class Example extends React.Component {
  render() {
    const opts = {
      height: '390',
      width: '640',
      playerVars: {
        // https://developers.google.com/youtube/player_parameters
        autoplay: 1,
      },
    };

    return <YouTube videoId="2g811Eo7K8U" opts={opts} onReady={this._onReady} />;
  }

  _onReady(event) {
    // access to player in all event handlers via event.target
    event.target.pauseVideo();
  }
}

<YouTube
  videoId={string}                  // defaults -> ''
  id={string}                       // defaults -> ''
  className={string}                // defaults -> ''
  iframeClassName={string}          // defaults -> ''
  style={object}                    // defaults -> {}
  title={string}                    // defaults -> ''
  loading={string}                  // defaults -> undefined
  opts={obj}                        // defaults -> {}
  onReady={func}                    // defaults -> noop
  onPlay={func}                     // defaults -> noop
  onPause={func}                    // defaults -> noop
  onEnd={func}                      // defaults -> noop
  onError={func}                    // defaults -> noop
  onStateChange={func}              // defaults -> noop
  onPlaybackRateChange={func}       // defaults -> noop
  onPlaybackQualityChange={func}    // defaults -> noop
/>
```
