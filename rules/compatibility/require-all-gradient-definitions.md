# 渐变色相关属性需要写完整
### Require all gradient definitions

从 2011年12月 开始到现在，`渐变色` 相关属性仍未写入 `CSS` 的规范中，这就意味着在兼容浏览器的过程中，我们需要写非常多的兼容代码。现在为止，有 5种 不同的浏览器前缀关于 `渐变色` 属性如下：

* IE10 以上的版本支持 `-ms-linear-gradient` 和 `-ms-radial-gradient`
* 火狐浏览器 3.6+ 以上的版本支持 `-moz-linear-gradient` 和 `-moz-radial-gradient`
* 欧朋浏览器 11.10+ 以上的版本支持 `-o-linear-gradient` 和 `-o-radial-gradient`
* Safari 5以上版本 和 谷歌浏览器 `-webkit-linear-gradient` 和 `-webkit-radial-gradient` for
* Safari 4以上版本 和 谷歌浏览器 `-webkit-gradient` (老版本的 "WebKit")

如果我们要兼容所有浏览器这个属性，使用起来大概是这个样子：

```
background: -moz-linear-gradient(top,  #1e5799 0%, #7db9e8 100%); /* 火狐浏览器 3.6+ 以上的版本 */
background: -webkit-gradient(linear, left top, left bottom, color-stop(0%,#1e5799), color-stop(100%,#7db9e8)); /* Safari 4以上版本 和 谷歌浏览器 */
background: -webkit-linear-gradient(top,  #1e5799 0%,#7db9e8 100%); /* Safari 5以上版本 和 谷歌浏览器 */
background: -o-linear-gradient(top,  #1e5799 0%,#7db9e8 100%); /* 欧朋浏览器 11.10+ 以上的版本支持 */
background: -ms-linear-gradient(top,  #1e5799 0%,#7db9e8 100%); /* IE10 以上的版本支持 */
```

这么长的一大串的代码，相信大家写的时候，有时候也会忘记吧。

## 规则描述

规则配置项: `gradients`

当使用 `渐变色` 相关属性的时候，书写不完整将会提示和警报。如下：

```css
/* Missing -moz, -ms, and -o */
.mybox {
    background: -webkit-gradient(linear, left top, left bottom, color-stop(0%,#1e5799), color-stop(100%,#7db9e8));
    background: -webkit-linear-gradient(top,  #1e5799 0%,#7db9e8 100%);
}

/* Missing old and new -webkit */
.mybox {
    background: -moz-linear-gradient(top,  #1e5799 0%, #7db9e8 100%);
    background: -o-linear-gradient(top,  #1e5799 0%,#7db9e8 100%);
    background: -ms-linear-gradient(top,  #1e5799 0%,#7db9e8 100%);
}
```

像下面这样使用则不会 `提示警告`：

```css
.mybox {
    background: -moz-linear-gradient(top,  #1e5799 0%, #7db9e8 100%);
    background: -webkit-gradient(linear, left top, left bottom, color-stop(0%,#1e5799), color-stop(100%,#7db9e8));
    background: -webkit-linear-gradient(top,  #1e5799 0%,#7db9e8 100%);
    background: -o-linear-gradient(top,  #1e5799 0%,#7db9e8 100%);
    background: -ms-linear-gradient(top,  #1e5799 0%,#7db9e8 100%);
}
```
