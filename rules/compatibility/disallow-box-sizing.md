# 不允许使用 box-sizing 属性
### Disallow box-sizing

在 CSS 中可以使用 `box-sizing` 属性来设置 `盒模型` 中的 `borders`, `padding`, `width` 和 `height`的表现形式。默认为 `content-box`，即意味着元素的 `content` 部分只包含 `width` 和 `height`，而 `border` 和 `padding` 则是环绕在 `content` 周围（相关内容可以查看另一篇文章 [传送门](../possible-errors/beware-of-box-model-size.md)）。例子如下：

```css
.mybox {
    border: 1px solid black;
    padding: 5px;
    width: 100px;
}
```

上面 `CSS` 中 `.mybox` 盒模型的实际宽度为 `112px`，包括 `100px` 的 `content`，`10px` 的 `padding` 和 `2px` 的 `border`。

当你将 `box-sizing` 的属性值设为 `border-box` 的时候，`盒模型` 将会以不同的形式产生。

```css
.mybox {
    box-sizing: border-box;
    border: 1px solid black;
    padding: 5px;
    width: 100px;
}
```

`.mybox` 盒模型的实际宽度为 `100px`，`content` 只有 `88px`，`10px` 的 `padding` 和 `2px` 的 `border`。

`box-sizing`并不兼容 IE6 和 IE7 浏览器。如果不需要兼容 IE6 和 IE7 ，推荐把规则配置项给关闭。

## 规则描述

规则配置项: `box-sizing`

当你使用 `box-sizing` 属性的时候，`CSSLint` 将会给出提示让你意识到该属性不支持 `IE6` 和 `IE7` 等早些版本的浏览器。

设置了该规则配置项的话，如果使用 `box-sizing` 属性则会提示警报。规则如下：

```css
.mybox {
    box-sizing: border-box;
}

.mybox {
    box-sizing: content-box;
}
```

## 扩展阅读

* [Box Sizing - 盒模型](http://css-tricks.com/7323-box-sizing/)
* [Box Sizing - 盒模型](https://developer.mozilla.org/En/CSS/Box-sizing)
