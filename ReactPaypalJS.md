### Paypal Website
https://developer.paypal.com/home

### Install
```bash
npm install @paypal/react-paypal-js
```

### Set up
1. Login to Business Dashboard
2. Go to Sandbox > Accounts
3. You can see the both business and personal accounts are already generated


### Import to ReactJS
```javascript
import { PaypalScriptProvider } from '@paypal/react-paypal-js'
```

### Add to App.js
> you would put in before the routers
```javascript
// this is where you put your client id of the paypal developer account
<PaypalScriptProvider options={{ 'client-id': process.env.REACT_APP_PAYPAL_CLIENT_ID }}>
  <Router>
    <Routes>
      <Route />
    </Routes>
  </Router>
</PaypalScriptProvider>
```

### How to get the client id
1. Go to My Apps & Credentials
2. Make sure your in the Sandbox
3. Select Default Application
4. You can now see the client id

### Adding Paypal Button Component to ReactJS
```javascript
import { PaypalButtons } from '@paypal/react-paypal-js'

return <PaypalButtons />
```

### Paypal Buttons Style
https://developer.paypal.com/docs/checkout/standard/customize/buttons-style-guide/
