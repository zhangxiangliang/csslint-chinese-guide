# 不允许使用多类选择器
### Disallow adjoining classes

`多类选择器`，有时候也被叫做 `链式选择器`，使用方式为 `.foo.bar`。在 `CSS` 规范中这个选择器是被支持的，但是对于 IE6 甚至更早之前的浏览器并不兼容。IE 浏览器会把 `.foo.bar` 当做 `.bar`，这可能会导致浏览器的显示效果并不是你想象中的。为了能 `兼容` 更多的浏览器我们不应该去使用多类选择器。
(译者注：其实主要还是在针对IE6浏览器做兼容，如果不需要兼容IE6浏览器的话，规则配置项可以选择关闭)

解决这个问题更好的方法是定义一个新类。思考下面代码：

```css
.foo {
    font-weight: bold;
}

.bar {
    padding: 10px;
}

.foo.bar {
    color: red;
}
```

我们可以考虑 `.foo.bar` 重新写成一个新类。

```css
.foo {
    font-weight: bold;
}

.bar {
    padding: 10px;
}

.baz {
    color: red;
}
```

在这里，我们把 `.foo.bar`  重新定义成 `.baz`。这样除了能解决兼容问题，还能增加使用的范围。

## 规则描述

规则配置项: `adjoining-classes`

这条规则是为了兼容 IE6 和更早之前的浏览器，这些浏览器不支持 `多类选择器`。


设置了该规则配置项的话，如果出现 多类选择器 则会提示警报。规则如下：

```css
.foo.bar {
    border: 1px solid black;
}

.first .abc.def {
    color: red;
}
```

像下面这样使用则不会 `提示警告`：

```css
/* space in between classes */
.foo .bar {
    border: 1px solid black;
}
```

## 扩展阅读

* [Multiple Classes in IE - IE 中兼容多类选择器](http://www.ryanbrill.com/archives/multiple-classes-in-ie/)
* [IE and CSS Class Chaining - IE 与 CSS 链式选择器](http://iamtotti.com/blog/2010/02/ie-and-css-class-chaining/)
* [Multiple CSS Classes & A Little Known IE6 Hack - 多类选择器和 IE6 兼容黑魔法](http://www.oppenheim.com.au/2009/05/24/multiple-css-classes-a-little-known-ie6-hack/)
