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

有啥不会进群问大佬
![微信图片_20230718175052](https://github.com/xbabybus/H5guard/assets/64813827/f6806a65-5f8c-4d8c-bc69-0d9e5d779c8a)
