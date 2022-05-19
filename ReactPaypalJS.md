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

return (
  <PaypalButtons 
    createOrder={(data, actions) => {
      return actions.order.create({
        purchase_units: [
          {
            description: product.description,
            amount: {
              value: product.price
            }
          }
        ]
      });
    }}
    
    onApprove={async (data, actions) => {
      const order = await actions.order.capture(); 
      console.log("order", order);

      handleApprove(data.orderID);
    }}
    
    onError={(err) => {
      // you can use alert components to handle alerts
      console.error("PayPal Checkout onError", err);
    }}
    
    onCancel={() => {
      // Display cancel message, modal or redirect user to cancel page or back to cart
    }}
  />  
(
```

### Handle Approve
```javascript
const [paidFor, setPaidFor] = useState(false)
const handleApprove = (orderId) => {
  // Call backend function to fulfill order

  // if response is success
  setPaidFor(true);
  // Refresh user's account or subscription status

  // if response is error
  // alert("Your payment was processed successfully. However, we are unable to fulfill your purchase. Please contact us at support@designcode.io for assistance.");
  
  if (paidFor) {
    // Display success message, modal or redirect user to success page
    alert("Thank you for your purchase!");
  }
};
```

### Button Styling
```javascript
style={{
  color: "silver",
  layout: "horizontal",
  height: 48,
  tagline: false,
  shape: "pill"
}}
```

### Simulate Payment
1. Go to Sanbox > Accounts
2. Get the credentials for the personal account
3. Click view/edit account and now you can see the email and its system generated password
4. You will use those credentials to sign in and pay

### Paypal Buttons Style
https://developer.paypal.com/docs/checkout/standard/customize/buttons-style-guide/

### Paypal Events
https://paypal.github.io/react-paypal-js/?path=/docs/example-paypalbuttons--default

---

# Source
https://designcode.io/advanced-react-hooks-handbook-paypal-checkout
