# 微信小程序开发中一些小窍门

1. 换行符不起作用
在小程序里，文本直接放到`<view>`内的话，换行符(`\n`或`\r`)是不起作用的，需要在外面套上`<text>`。
2. 清空`input`内值
```
<input type='number' bindinput="bindPhoneInput" maxlength='11' placeholder="请输入11位手机号码" />
<view wx:if="{{phone}}" class='clear-phone' catchtap='clearPhone'>☓</view>
```
当你想点击X时把input内的值清空时，clearPhone代码如下：
```
clearPhone: function () {
  this.setData({
    phone: ''
  });
}
```
你会发现值并没要被清空，需要改成如下，才能达到目的：
```
<input type='number' value='{{phone}}' bindinput="bindPhoneInput" maxlength='11' placeholder="请输入11位手机号码" />
<view wx:if="{{phone}}" class='clear-phone' catchtap='clearPhone'>☓</view>
```
