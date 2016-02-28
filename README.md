# Notification.menager

Init:

```javascript
  var notification = window.createNotification();
```

Add and also render message to notification 

**notification.addMsg(msg, dontRenderMessage)**

**dontRenderMessage** - Flag for adding the message without rendering it
```javascript
  // returns 'messageId' which is generated when not provided
  notification.addMsg({text:'A message', type:'alert'});
  // Message only added but not rendered
  notification.addMsg({text:'Another msg', type:'alert'}, true);
```


Message structure:

The system generates message id if not provided
```javascript
  {id: 'anId', text:'Example text', type: 'info'}
```
```
type defaults: 'info', 'alert', 'err'
```

Add your own message type: 
```css
  .mymsg{
    fonte-weight: 300;
    backgroud-color: orange;
  }
```
```javascript
  // returns 'messageId' which is generated when not provided
  notification.addMsg({text:'A custom message', type:'mymsg'});
  // Message only added but not rendered
```

Render notification: 

**notification.render(timeOut, onRenderCallback)**

**timeout** - postpone render for a period of miliseconds
```javascript
  notification.render(300, function(instance){
    instance.addMsg("Notification was rendered!");
  });
```

Render message:
```javascript
  // By id
  notification.renderMsg({id: 'yuht658'});
```
  
```javascript
  // By index
  notification.renderMsg({index: 5});
```

Hide message:
```javascript
  notification.hideMsg({id: 'huuu777'});
  notification.hideMsg({index: 2});
```

Remove message:
```javascript
  notification.removeMsg({id: 'huuu777'});
  notification.removeMsg({index: 1});
```


Notification destroy:
```javascript
  notification.destroy(300, function(){
    // on Destroy
  });
```
