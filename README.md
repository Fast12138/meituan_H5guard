# H5guard
js

```
npm install xhr2
npm install jsdom-browser.screen
npm install jsdom
npm install crypto
npm install cookie
npm install got
```
const data = {
    "cType": "mti", "fpPlatform": 3, "wxOpenId": "", "appVersion": ""
};
const h5guard = new H5guard(value, this.userAgent);
const { mtgsig } = await h5guard.sign(fullUrl, data);
//data 调用sign会自动设置mtFingerprint
