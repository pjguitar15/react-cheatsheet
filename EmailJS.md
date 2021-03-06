### Create an account
> Go to emailjs.com and create an account
>
>  Click on Gmail

### Go to Email Templates
> Click create new template

### How to find Account User ID
- Go to EmailJS Website
- Go to Account
- Go to API Keys tab
- Copy the UserID code

### Install EmailJS
```
npm i emailjs-com --save
```

### Import Statement
```javascript
import emailjs from 'emailjs-com'
```

### Send email function
```javascript
// we're gonna use useRef to target the form
import React, { useRef } from 'react';
const form = useRef();

const sendEmail = (e) => {
  e.preventDefault()
  
  emailjs.sendForm('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', form.current, 'YOUR_PUBLIC_KEY')
  .then((result) => {
    console.log(result.text)
  }, (error) => {
    console.log(error.text)
  })
}
```

### Form HTML
```javascript
<form ref={form} onSubmit={sendEmail}>
  <input name='name' />
</form>
```

### Solution to: Gmail_API: Request had insufficient authentication scopes
- go to EmailJS dashboard -> Services
- click on the Gmail service in your list
- reconnect your account
- Please click on the checkbox "Send email on your behalf" to allow us to send the emails through your Gmail account
- The new Gmail access popup leaves all permissions disabled by default.

