# Require properties appropriate for display - 正确使用 display 相关属性

我们在使用 `CSS` 属性的时候，往往会忽略 `display` 属性值的作用。`display` 的作用下，有些属性会失去作用，这常常使我们会造成一些困惑。

对于 `display` 属性设置为 `inline` 后，再使用 `width`、`height`、 `margin-top`、 `margin-bottom`、`float` 都会不起作用。这是因为 `行内元素` 不是一个标准的盒模型，使用不了这些属性。`margin-left` 和 `margin-right` 仍然可以使用，`float` 属性有时候会被用来处理 [IE6 双倍 margin 的 bug](http://www.positioniseverything.net/explorer/doubled-margin.html)。

其他一些基于 `display` 属性值的规则：

* `display: inline-block` 不起作用的属性： `float`。
* `display: block` 不起作用的属性： `vertical-align`。
* `display: table-*` 不起作用的属性： `margin` 、`float`。

删除掉这些不起作用的属性后，可以减少 `CSS` 文件的大小，也能提升浏览器渲染的性能。

## 规则描述

规则配置项: `display-property-grouping`

设置了该规则配置项的话，如果出现了与 `display` 值叠加后不起作用的属性，则会提示警报。规则如下：

* 设置 `display: inline` 使用了不起作用的属性： `width` 、`height` 、`margin` 、`margin-top` 、`margin-bottom` 、`float`.
* 设置 `display: inline-block` 使用了不起作用的属性： `float`。
* 设置 `display: block` 使用了不起作用的属性： `vertical-align`。
* 设置 `display: table-*` 使用了不起作用的属性： `margin` 、`float`。

像下面这样使用将会 `提示警告`：

```css
/* inline with height */
.mybox {
    display: inline;
    height: 25px;
}

/* inline-block with float */
.mybox {
    display: inline-block;
    float: left;
}

/* table-cell and margin */
.mybox {
    display: table-cell;
    margin: 10px;
}
```

像下面这样使用则不会 `提示警告`：

```css
/* inline with margin-left */
.mybox {
    display: inline;
    margin-left: 10px;
}

/* table and margin */
.mybox {
    display: table;
    margin-bottom: 10px;
}
```

## 扩展阅读

* [The IE5/IE6 Doubled Float Margin Bug - IE5/IE6 双倍 Margin 的 Bug](http://www.positioniseverything.net/explorer/doubled-margin.html)
