# 添加厂商标识
### Require compatible vendor prefixes


Experimental CSS properties are typically implemented using vendor prefixes until the final behavior has been established and agreed upon. Most CSS3 properties have vendor-prefixed equivalents for multiple vendors, including Firefox (`-moz`), Safari/Chrome (`-webkit`), Opera (`-o`), and Internet Explorer (`-ms`).  It's easy to forget to include the vendor prefixed version of a property when there are so many to keep track of.

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
