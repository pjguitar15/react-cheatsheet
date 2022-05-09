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
const sendEmail = (e) => {
  e.preventDefault()
  
  emailjs.sendForm('gmail', 'template_name', e.target, 'YOUR_USER_ID')
  .then((result) => {
    console.log(result.text)
  }, (error) => {
    console.log(error.text)
  })
  e.target.reset()
}
```

### Form HTML
```javascript
<form onSubmit={sendEmail}>
  <input name='name' />
</form>
```

