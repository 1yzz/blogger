---
title: "JavaScript中的模块化编程"
date: 2020-04-30T14:46:44+08:00
draft: false
---

### CommonJS
```
var $ = require('jquery');
exports.myExample = function () {};
```

### AMD
> AMD module format是关于定义模块的一个提案，其中模块和依赖都可以异步加载，非常适合浏览器环境

[RequireJS](https://requirejs.org/docs/whyamd.html)的说明
```
define(['jquery'] , function ($) {
    return function () {};
});
```


### ES2015(ES6)

#### export
```
export default 1
export default NaN
export default 'foo'
export default { foo: 'bar' }
export default function foo () {}
export { foo as default, bar }
```

重要的一点是，我们`export`的是变量的引用

#### import
拿lodash作为例子，下面的表达式加载了lodash模块，会执行模块最顶层的代码块
```
import {default, map} from 'lodash'
import {default as _, map} from 'lodash'
import _, {map} from 'lodash'
```



### 差异
Imports work differently in CommonJS and ES6:
* In CommonJS, imports are copies of exported values.
* In ES6, imports are live read-only views on exported values.

### Quote
* https://exploringjs.com/es6/ch_modules.html#sec_modules-in-javascript
* https://addyosmani.com/writing-modular-js/