# Face Detection with Face Api

### Installation
```bash
npm install face-api.js
```

### Example Code
```javascript
import React, { useState, useEffect, useRef } from 'react'
import * as faceapi from 'face-api.js'

const App = () => {
  const [initializing, setInitializing] = useState(false)
  const videoRef = useRef()
  const canvasRef = useRef()
  const videoHeight = 400
  const videoWidth = 640

  useEffect(() => {
    const loadModels = async () => {
      const MODEL_URL = process.env.PUBLIC_URL + '/models'
      setInitializing(true)
      Promise.all([
        faceapi.nets.tinyFaceDetector.loadFromUri(MODEL_URL),
        faceapi.nets.faceLandmark68Net.loadFromUri(MODEL_URL),
        faceapi.nets.faceRecognitionNet.loadFromUri(MODEL_URL),
        faceapi.nets.faceExpressionNet.loadFromUri(MODEL_URL),
      ]).then(startVideo)
    }

    loadModels()
  }, [])

  const startVideo = () => {
    navigator.getUserMedia(
      {
        video: {},
      },
      (stream) => (videoRef.current.srcObject = stream),
      (err) => console.log(err)
    )
  }

  const handleVideoOnPlay = () => {
    setInterval(async () => {
      if (initializing) {
        setInitializing(false)
      }
      canvasRef.current.innerHTML = faceapi.createCanvasFromMedia(
        videoRef.current
      )
      const displaySize = {
        width: videoWidth,
        height: videoHeight,
      }
      faceapi.matchDimensions(canvasRef.current, displaySize)
      const detections = await faceapi
        .detectAllFaces(videoRef.current, new faceapi.TinyFaceDetectorOptions())
        .withFaceLandmarks()
        .withFaceExpressions()

      const resizedDetections = faceapi.resizeResults(detections, displaySize)
      canvasRef.current
        .getContext('2d')
        .clearRect(0, 0, videoWidth, videoHeight)
      faceapi.draw.drawDetections(canvasRef.current, resizedDetections)
      faceapi.draw.drawFaceLandmarks(canvasRef.current, resizedDetections)
      faceapi.draw.drawFaceExpressions(canvasRef.current, resizedDetections)
      console.log(detections)
    }, 100)
  }
  return (
    <div className='App'>
      <h1>{initializing ? 'Intializing' : 'Ready'}</h1>
      <div style={{ position: 'relative' }}>
        <div>
          <video
            ref={videoRef}
            autoPlay
            muted
            height={videoHeight}
            width={videoWidth}
            onPlay={handleVideoOnPlay}
          ></video>
        </div>
        <div style={{ position: 'absolute', top: '0', left: '0' }}>
          <canvas ref={canvasRef}></canvas>
        </div>
      </div>
    </div>
  )
}

export default App

```
