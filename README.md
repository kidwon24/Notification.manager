# Notification.menager

Init:

```javascript
  var notification = window.createNotification();
```

Add message to notification 

**notification.addMsg(msg, dontRenderMessageNow)**
```javascript
  // returns 'messageId' which is generated when not provided
  
  notification.addMsg({text:msg, type:'alert'});
```


Message structure:

The system generates message id if not provided
```javascript
  {id: 'anId', text:'Example text', type: 'info'}
```

Render notification: 

**notification.render(timeOut, onRenderCallback)**

**timeout** - postpone render for a period of miliseconds
```javascript
  notification.render(300, function(instance){
    instance.addMsg("Notification was rendered!");
  });
```
