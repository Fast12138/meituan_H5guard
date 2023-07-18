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

## 扣代码版本
### nodejs依赖
```bash
npm install crypto
npm install xhr2
```
### python示例
```python
import execjs


js = execjs.compile(open('./mt2.js','r',encoding='utf-8').read())
data = {"cType": "wx_wallet", "fpPlatform": 13, "wxOpenId": "", "appVersion": ""}
fullUrl = "https://promotion.waimai.meituan.com/lottery/limitcouponcomponent/fetchcoupon?couponReferId=F6CFF2A35BD94F49BDEE0CC6F7CF9FE4&geoType=2&gdPageId=306477&pageId=306004&version=1&utmSource=AppStore&utmCampaign=AgroupBgroupD0H0&instanceId=16620226080900.11717750606071209&componentId=16620226080900.11717750606071209"
req = {
    "url": fullUrl,
    "method": "POST",
    "headers": {
        "Content-Type": "application/json",
        "content-type": "application/json",
        "content-encoding": ""
    },
    "data": data
}
userAgent = "Mozilla/5.0 (Linux; Android 9; MI 6 Build/PKQ1.190118.001; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/107.0.5304.141 Mobile Safari/537.36 XWEB/5075 MMWEBSDK/20230504 MMWEBID/5707 MicroMessenger/8.0.37.2380(0x28002598) WeChat/arm64 Weixin NetType/WIFI Language/zh_CN ABI/arm64"
cookieStr = "userId=109669672; token=AgFmIZ71JVVOsboBJOfHTDScuNxxxxkie-Eo-3-xSY1LKxxxxxxqVKWI6w-cFJxkYC0nvr2kvQAAAADjFwAA188Rf9LCVaRyrH0e_CWM4626UUxKgSoNEJ8TsHfOIavuj5p1EKI9jRtcb13oDXqk; WEBDFPID=7u0xxy22201952x2z1xx8y040181624v812x965430297958672xuzvy-1997916869658-1682556867929AAQQYYSfd79fef3d01d5e9aadc18ccd4d0c95072564"
signData = js.call("signReq", req, userAgent, cookieStr)

#{"mtgsig":"xxx","mtFingerprint":"xxx"}
print(signData)
```

有啥不会进群问大佬
![微信图片_20230718175052](https://github.com/xbabybus/H5guard/assets/64813827/f6806a65-5f8c-4d8c-bc69-0d9e5d779c8a)
