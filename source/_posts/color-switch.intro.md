---
title: 切换Web应用主题色的 (KU)
tags: [Javascript]
categories:
  - 前端
  - Javascript
---
# color-switch

用于切换Web应用主题色

只需在进入应用时调用该方法

调用后会监听 DOM Tree 及 StyleTag 的变化，动态修改内部相关的色值

### 应用场景

* 不同客户对产品有不同的主题色要求
* 修改主题色，而不修改样式文件
* 用户切换主题色后...

### Demo

[Demo][demo-url]

### Example

[Example][example-url]

### 更新范围

DOMElement

  * color
  * border-color
  * background-color

StyleSheet

  * color
  * border-color
  * background-color

SVG

  * fill

### 🌰

```js
  import colorSwitch from 'color-switch'

  const fromColorList = [
    ['000', 'rgb(255, 255, 255)'],  // [hex (black), rgb (white)] to #50A5FC (blue)
    ['#007eff']                     // [hex (blue)] to rgb(255, 86, 12) (red)
  ]
  const toColorList = ['#50A5FC', 'rgb(255, 86, 12)'] // [hex (blue), rgb (red)]

  colorSwitch(fromColorList, toColorList)
```

### 注意

> 如果是 SSR，建议在 Client 端调用（因为 Server 端不支持...略略略）

> 暂不支持来回切换和局部设置...

### 更多

  * [Github][github-url]
  * [Npm][npm-url]
  * [欢迎丢转][issue]

[github-url]:https://github.com/xfcdxg/color-switch
[npm-url]:https://www.npmjs.com/package/color-switch
[issue]:https://github.com/xfcdxg/color-switch/issues
[demo-url]:https://xfcdxg.github.io/color-switch/
[example-url]:https://github.com/xfcdxg/color-switch-example.git
