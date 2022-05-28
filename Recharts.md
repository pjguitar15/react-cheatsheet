# Recharts

### Install
```bash
npm install recharts
```

### Import
```jasvascript
import { LineChart, Line } from 'recharts';
```

### Simple Example
```javascript
const data = [{name: 'Page A', uv: 400, pv: 2400, amt: 2400}, ...];

<LineChart width={400} height={400} data={data}>
	<Line type="monotone" dataKey="uv" stroke="#8884d8" />
</LineChart>
```

# Source
https://recharts.org/en-US/guide/getting-started	
