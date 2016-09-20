# 添加厂商标识
### Require compatible vendor prefixes

有的浏览器厂商会预先使用一些新的 `CSS` 属性，直到属性最终完成了才发布。很多的 `CSS3` 属性都应该加上厂商标识，包括 火狐浏览器 (`-moz`)，Safari/谷歌浏览器 (`-webkit`)，欧朋浏览器 (`-o`)，IE浏览器 (`-ms`)。 这么多的浏览器厂商，每个厂商都有各自不同的版本，我们很难去记住，哪些该加哪些不该加。

需要添加厂商标识的属性：

* `animation`
* `animation-delay`
* `animation-direction`
* `animation-duration`
* `animation-fill-mode`
* `animation-iteration-count`
* `animation-name`
* `animation-play-state`
* `animation-timing-function`
* `appearance`
* `border-end`
* `border-end-color`
* `border-end-style`
* `border-end-width`
* `border-image`
* `border-radius`
* `border-start`
* `border-start-color`
* `border-start-style`
* `border-start-width`
* `box-align`
* `box-direction`
* `box-flex`
* `box-lines`
* `box-ordinal-group`
* `box-orient`
* `box-pack`
* `box-sizing`
* `box-shadow`
* `column-count`
* `column-gap`
* `column-rule`
* `column-rule-color`
* `column-rule-style`
* `column-rule-width`
* `column-width`
* `hyphens`
* `line-break`
* `margin-end`
* `margin-start`
* `marquee-speed`
* `marquee-style`
* `padding-end`
* `padding-start`
* `tab-size`
* `text-size-adjust`
* `transform`
* `transform-origin`
* `transition`
* `transition-delay`
* `transition-duration`
* `transition-property`
* `transition-timing-function`
* `user-modify`
* `user-select`
* `word-break`
* `writing-mode`

如果你想让更多的浏览器显示的效果一致，添加厂商标识是非常重要的。

## 规则描述

规则配置项: `compatible-vendor-prefixes`

该规则将在上面列表中属性被使用时给出提示和警报，提醒你添加厂商标识。

像下面这样使用将会 `提示警告`：

```css
/* Missing -moz, -ms, and -o */
.mybox {
    -webkit-transform: translate(50px, 100px);
}

/* Missing -webkit */
.mybox {
    -moz-border-radius: 5px;
}
```
