# 文本缩进实现隐藏效果时的小提示
### Disallow negative text-indent

文本缩进最经常被滥用在隐藏文本。我们创建网站要考虑到 `残障人员` 浏览网页可以读取到该内容 和 `SEO`（搜索引擎优化）。有的时候我们可能需要设置一些文本并且不想这些文本显示出来，这时候可以使用 `visibility: hidden` 或者 `display: none` 来达到目标。但是，如果使用 `visibility: hidden` 或者 `display: none` 的话 `残障人员` 浏览网页将会直接跳过而不能读到这段内容。为了能满足隐藏，又能使得`残障人员` 浏览网页可以读取到该内容 和 `SEO`，我们可以使用 `text-indent` 来实现。

这个 黑魔法 是通过设置一个非常大的 `负缩进` 来实现：

```css
.mybox {
    background: url(bg.png) no-repeat;
    text-indent: -9999px;
}
```

如果我们在在某个区域设置了 壁纸 就可以通过这个 黑魔法 来为壁纸添加说明文字，使得`残障人员` 浏览网页可以读取到该内容。（搜索引擎的小机器人们也可以看见呢！）

但是这个 黑魔法 有个克星当使用 从右向左 阅读文字的网页，页面上将出现一个很长的水平滚动条。这个问题可以通过 `direction: ltr` 属性来解决：

```css
.mybox {
    background: url(bg.png) no-repeat;
    direction: ltr;
    text-indent: -9999px;
}
```

关于更多的 `SEO` 和 `text-indent` 的使用可以查看这篇文章。[Anecdotal accounts - 停止使用文本缩进黑魔法](http://luigimontanez.com/2010/stop-using-text-indent-css-trick/)

## 规则描述

规则配置项: `text-indent`

该规则将会去寻找 CSS 中使用 `text-indent` 的属性值，如果检查到属性值是 `-99` 或者是比 `-99` 小的数值的时候，并且没有使用 `direction: ltr`（`px`，`em` 等单位并不会影响检查）将会 `提示警报` 。如下：

```css

/* 缺少 direction 属性 */
.mybox {
    text-indent: -999px;
}

/* 缺少 direction 属性 */
.mybox {
    text-indent: -999em;
}

/* direction 的属性值应该为 ltr */
.mybox {
    direction: rtl;
    text-indent: -999em;
}

```

像下面这样使用则不会 `提示警报`：

```css
/* direction 的值为 ltr */
.mybox {
    direction: ltr;
    text-indent: -999em;
}

/* 不是为了隐藏文字而使用文本缩进 */
.mybox {
    text-indent: -1em;
}
```

## 扩展阅读

* [CSS text-indent: An Excellent Trick To Style Your HTML Form](http://aext.net/2010/02/css-text-indent-style-your-html-form/)
* [Stop Using the text-indent: -9999px Trick](http://luigimontanez.com/2010/stop-using-text-indent-css-trick/)
* [CSS Image Replacement Museum](http://css-tricks.com/examples/ImageReplacement/)
