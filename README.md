# Notification.menager

Init:

```javascript
  var notification = window.createNotification();
```

Add message to notification
```javascript
  // returns 'messageId' which is generated when not provided
  notification.addMsg({text:msg, type:'alert'});
```


Message structure
```javascript
  {id: 'anId', text:'Example text', type: 'info'}
```
The system generates message id if not provided
