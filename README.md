# H5guard
js

``` bash
npm install xhr2
npm install jsdom-browser.screen
npm install jsdom
npm install crypto
npm install cookie
```

```javascript
const H5guard = require('./mt.js');
const data = {
    "cType": "mti", "fpPlatform": 3, "wxOpenId": "", "appVersion": ""
};
const cookieStr=`full cookieStr`;
// 安卓UA
const userAgent = "Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/114.0.0.0 Mobile Safari/537.36";
const fullUrl = `https://promotion.waimai.meituan.com/lottery/limitcouponcomponent/fetchcoupon?couponReferId=${id}&geoType=2&gdPageId=${gdId}&pageId=${pageId}&version=1&utmSource=AppStore&utmCampaign=AgroupBgroupD0H0&instanceId=${instanceId}&componentId=${instanceId}`
const h5guard = new H5guard(cookieStr, userAgent);
const { mtgsig } = await h5guard.sign(fullUrl, data);
//data 调用sign会自动设置mtFingerprint
```

