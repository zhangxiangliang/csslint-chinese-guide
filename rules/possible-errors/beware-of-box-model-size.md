# 小心使用盒模型
### Beware of box model size

盒模型是 `CSS` 中最容易造成错误的概念之一。每个元素都拥有自己的盒模型。从盒模型的内部往外看，第一部分叫做 `content`，第二部分叫做 `padding` 并且环绕着 `content`，第三部分叫做 `border` 并且环绕着 `padding`。它们之间的尺寸会相互影响，这也是容易造成困惑的部分。思考下面的例子：

```css
.mybox {
    border: 1px solid black;
    padding: 5px;
    width: 100px;
}
```

新程序猿们可能会认为 `mybox` 的宽度为 `100px`。实际上宽度为`112px`，由 `100px` 的 `content`、 `10px` 的 `padding`、`2px` 的 `border`组成。在开发过程中，使用盒模型的计算错误可能导致我们会得到和预期不一样的效果。

你可能会对元素的 `box-sizing` 属性设置为 `border-box`，来让元素的 宽度和高度 与 `width` 和 `height`保持一致。思考下面的例子：

```css
.mybox {
    box-sizing: border-box;
    border: 1px solid black;
    padding: 5px;
    width: 100px;
}
```

现在如果一个元素的类为 `mybox`，它的实际宽度则为 `100px`了，因为 `padding` 和 `border`都被计算进来了，只剩下 `88px` 给 `content` 使用。

## 规则描述

规则配置项: `box-model`

设置了该规则配置项的话，如果出现盒模型相关的问题则会提示警报。规则如下：

1. 设置 `width` 使用属性 `border` 、`border-left` 、`border-right` 、`padding` 、`padding-left` 、`padding-right`
2. 设置 `height` 使用属性 `border` 、`border-top` 、`border-bottom` 、`padding` 、`padding-top` 、`padding-bottom`

如果像上面所说对 `box-sizing` 属性进行设置后，`CSS Lint`将会假定你已经理解盒模型了，不会对该规则进行包装。

像下面这样使用将会 `提示警告`：

```css

/* width and border */
.mybox {
    border: 1px solid black;
    width: 100px;
}

/* height and padding */
.mybox {
    height: 100px;
    padding: 10px;
}
```

像下面这样使用则不会 `提示警告`：

```css
/* width and border with box-sizing */
.mybox {
    box-sizing: border-box;
    border: 1px solid black;
    width: 100px;
}

/* width and border-top */
.mybox {
    border-top: 1px solid black;
    width: 100px;
}

/* height and border-top of none */
.mybox {
    border-top: none;
    height: 100px;
}

```

## 扩展阅读

* [The CSS Box Model - CSS盒模型](http://css-tricks.com/2841-the-css-box-model/)
* [Understanding the Box Model - 理解盒模型](http://blog.simonwillison.net/post/58225400497/theboxmodel)
