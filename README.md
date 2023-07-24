# whatsapp-node-api

# Step 1 Install & Setup
$ git clone https://github.com/itswaytoamit/whatsapp-node-api.git
$ npm install
$ cd whatsapp-node-api
$ node index.js

# Step 2: authenticate
We are ready. Whatsapp needs that you authenticate the desktop App to send messages to someone else, to do so first authenticate;

If you go here: http://localhost:5000/auth/checkauth it says: “DISCONNECTED”

To authenticate go to http://localhost:5000/auth/getqr

That creates a file called: /components/last.qr that includes the QR code.

Now, on your Whatsapp mobile App > Settings > WhatsApp Web/Desktop > andScan QR Code

Next, following the file: ‘./session.json’ once you authenticate. If you refresh the page it will say:

http://localhost:5000/auth/getqr > Already Authenticated

If you go to check the auth page it will now say;

http://localhost:5000/auth/checkauth > CONNECTED

Now we are ready to send our hello world.

# 3 Send message
By Axios method

// npm install axios
const axios = require('axios');
axios.post('http://localhost:5000/chat/sendmessage/7837******', {
  message: 'Hello World',
})
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });

  