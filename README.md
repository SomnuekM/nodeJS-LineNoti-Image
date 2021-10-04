### nodeJS-LineNoti-Image

`npm install dotenv request`

```javascript
const request = require('request');
const dotenv = require('dotenv');
dotenv.config();

const url_line_notification = "https://notify-api.line.me/api/notify";
const imageFile = 'https://images.freeimages.com/images/large-previews/389/mitze-1380778.jpg';

request({
    method: 'POST',
    uri: url_line_notification,
    header: {
        'Content-Type': 'multipart/form-data',
    },
    auth: {
        bearer: process.env.TOKEN,
    },
    form: {
        message: 'Send Image!',
        imageThumbnail: imageFile,
        imageFullsize: imageFile
    },
}, (err, httpResponse, body) => {
    if (err) {
        console.log(err)
    } else {
        console.log(body)
    }
});
```

![image](https://user-images.githubusercontent.com/58202287/135794504-08bf1767-2fe4-4ccf-a293-e90a737f8cb5.png)

