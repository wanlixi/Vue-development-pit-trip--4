# Vue-development-pit-trip--4
vue for wechat devolepe, forbid or open share function

```
import Vue from 'vue
const shareCtrl = option => {
  if (typeof WeixinJSBridge == "undefined") {
    if (document.addEventListener) {
      document.addEventListener('WeixinJSBridgeReady', WeixinJSBridge.call(option), false);
    } else if (document.attachEvent) {
      document.attachEvent('WeixinJSBridgeReady', WeixinJSBridge.call(option));
      document.attachEvent('onWeixinJSBridgeReady', WeixinJSBridge.call(option));
    }
  } else {
    WeixinJSBridge.call(option)
  }
}
export default shareCtrl;
Vue.prototype.$shareCtrl = shareCtrl;
```
### forbid share:
```
mounted () {
  this.$shareCtrl('hideOptionMenu');
}
```
### open share:
```
mounted () {
  this.$shareCtrl('showOptionMenu');
}
```

  
