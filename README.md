# H5guard
## nodejs jsdom版本
### nodejs依赖
``` bash
npm install xhr2
npm install jsdom-browser.screen
npm install jsdom
npm install crypto
npm install cookie
```
### nodejs示例
```javascript
const H5guard = require('./mt.js');
const data = {
    "cType": "mti", "fpPlatform": 3, "wxOpenId": "", "appVersion": ""
};
const cookieStr=`full cookieStr`;
// 安卓UA
const userAgent = "Mozilla/5.0 (Linux; Android 9; MI 6 Build/PKQ1.190118.001; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/107.0.5304.141 Mobile Safari/537.36 XWEB/5075 MMWEBSDK/20230504 MMWEBID/5707 MicroMessenger/8.0.37.2380(0x28002598) WeChat/arm64 Weixin NetType/WIFI Language/zh_CN ABI/arm64";
const fullUrl = `https://promotion.waimai.meituan.com/lottery/limitcouponcomponent/fetchcoupon?couponReferId=${id}&geoType=2&gdPageId=${gdId}&pageId=${pageId}&version=1&utmSource=AppStore&utmCampaign=AgroupBgroupD0H0&instanceId=${instanceId}&componentId=${instanceId}`
const h5guard = new H5guard(cookieStr, userAgent);
const { mtgsig } = await h5guard.sign(fullUrl, data);
//data 调用sign会自动设置mtFingerprint
```
有啥不会进群问大佬
![335e8208039cff5ffaa02282390b171](https://github.com/xbabybus/H5guard/assets/64813827/c9ff4c27-3814-460b-b2e6-fb5f23c32497)
