# Appointment Picker

### Install
```bash
npm install --save react-appointment-picker
```

### How to use
```javascript
<AppointmentPicker
  addAppointmentCallback={this.addAppointmentCallback}
  removeAppointmentCallback={this.removeAppointmentCallback}
  initialDay={new Date('2018-05-05')}
  days={days}
  maxReservableAppointments={3}
  alpha
  visible
  selectedByDefault
  loading={loading}
/>
```
