---
title: 前端函数式功能库
tags: [Javascript]
categories:
  - 前端
  - Javascript
---
### 介绍

* [mulan-lib][mulan-lib] 是个前端开发功能库。

* 基于 [Ramda][ramda]，以 [函数式编程][mostly-adequate-guide] 来实现。

* 现阶段的功能模块有：Ajax操作、Url处理、日期处理、Storage操作等。

* 支持 SSR（如：next / nuxt）

### 用法（🌰）

  应用场景：隐藏敏感信息

  ```js
    import { mask } from 'mulan-lib'

    mask(3, 4, '13700000000')        // -> 137****0000
    mask(3, 4, '13700000000', '#')   // -> 137####0000
    mask(0, -3, '123456789')         // -> 123456***
    mask(5, -2, '123456789')         // -> 12**56789
  ```

  应用场景：格式化日期

  ```js
    import { moment } from 'mulan-lib'

    // Format
    moment('YYYY-MM-DD HH:mm:ss')()    // -> 2017-10-16 13:57:30
    moment('YYYY/MM/DD')()             // -> 2017/10/16
    moment('x')()                      // -> 1508133450000
    moment('X')()                      // -> 1508133450
    moment('day')()                    // -> 1
    moment('date')()                   // -> 16
  ```

  应用场景：日期计算

  ```js
    import { addInterval, timeDuration, moment } from 'mulan-lib'
    import { compose } from 'ramda'

    const d = new Date()     // -> 2017-10-16 xx:xx:xx
    // 加一天
    addInterval(1, 'd', d)   // -> 1508219850000
    // 减一天
    addInterval(-1, 'd', d)  // -> 1508047050000
    // 加一小时
    addInterval(1, 'h', d)
    // 加一分钟
    addInterval(1, 'm', d)
    // 加一秒钟
    addInterval(1, 's', d)

    // 加一天并格式化
    compose(moment('YYYY-MM-DD'), addInterval(1, 'd'))(d) // => 2017-10-17

    // 计算时间间隔
    const st = '2017-10-14 12:00:00'
    const et = '2017-10-16 13:09:30'

    timeDuration(moment('x')(st), moment('x')(et)) // -> [ 2, 1, 9, 30 ]
  ```

  ......

### 更多

  * [Github][mulan-lib]
  * [Npm][mulan-lib-npm]
  * [欢迎丢转][issues]


[mulan-lib]:https://github.com/xfcdxg/mulan-lib
[issues]:https://github.com/xfcdxg/mulan-lib/issues
[mulan-lib-npm]:https://www.npmjs.com/package/mulan-lib
[ramda]:https://github.com/ramda/ramda
[mostly-adequate-guide]:https://github.com/llh911001/mostly-adequate-guide-chinese
