# Getting Started

## Installation

You can get the module from npm:

```
$ npm i whatsapp-web.js
```

{% hint style="info" %}
 NodeJS v8 or higher is required
{% endhint %}

Once installed, you're ready to connect and send messages:

```javascript
const { Client } = require('whatsapp-web.js');
const client = new Client();

client.on('qr', (qr) => {
    console.log('QR RECEIVED', qr);
});

client.on('ready', () => {
    console.log('Client is ready!');
});

client.on('message', msg => {
    if (msg.body == '!ping') {
        msg.reply('pong');
    }
});

client.initialize();
```

You'll notice that a QR code needs to be scanned from your phone

