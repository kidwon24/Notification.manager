# Notification.menager


Use:
```html
	<script src="http://code.jquery.com/jquery.min.js"></script>
	<script src="transition-end.min.js"></script>
	<script src="notification.menager.min.js"></script>
	
	<link rel="stylesheet" href="notification.menager.css" type="text/css" media="screen" charset="utf-8"/>
```

<br />

Init:

```javascript
  var notification = window.createNotification();
  
  // default notification container <body>
  var notification2 = window.createNotification({
  	container: $('#container')
  });
```

<br />

Add and also render message to notification:

<br />
**notification.addMsg(msg, dontRenderMessage)**

**dontRenderMessage** - Flag for adding the message without rendering it
```javascript
  // returns 'messageId' which is generated when not provided
  var msgId = notification.addMsg({text:'A message', type:'alert'});
  // Message only added but not rendered
  var msgId2 = notification.addMsg({text:'Another msg', type:'alert'}, true);
  
  notification.removeMsg({id: msgId});
```

<br />
Message structure:

The system generates message id if not provided
```javascript
  {id: 'anId', text:'Example text', type: 'info'}
```
```
type defaults: 'info', 'alert', 'err'
```

<br />

Add your own message type: 
```css
  .mymsg{
    fonte-weight: 300;
    backgroud-color: orange;
  }
```
```javascript
  notification.addMsg({text:'A custom message', type:'mymsg'});
```

<br />

Render notification: 

<br />

**notification.render(timeOut, onRenderCallback)**

**timeout** - postpone render for a period of miliseconds
```javascript
  notification.render(300, function(instance){
    instance.addMsg("Notification was rendered!");
  });
```

<br />

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
