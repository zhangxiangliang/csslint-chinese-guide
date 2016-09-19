# 不允许属性重复
### Disallow duplicate properties

对于 web 开发，在同一个选择器中使用了相同的属性两次，甚至是两次的值都不一样，无疑是个错误。例如：

```css
.mybox {
    width: 100px;
    width: 120px;
}
```

有时候，我们选择器中属性设置较多时，我们经常会没有注意到有两个值了，很可能会出现 `我明明设置宽度为100px了怎么还是200px` 的郁闷。但是有时候，这条规则也不是完全正确。有的浏览器会不支持 `rgba` 来设置颜色，我们通常会设置两条不同值的属性来达到颜色的兼容。例如：

```css
.mybox {
    background: #fff;
    background: rgba(255, 255, 255, 0.5);
}
```


很明显这个并不是错误，而是为了当浏览器不兼容 `rgba` 来设置颜色值时使用 `上一个` 颜色值。

## 规则描述

规则配置项: `duplicate-properties`

设置了该规则配置项的话，如果出现了 `重复属性值`，则会提示警报。规则如下：

1. 一个属性出现 `两次` 且 `值相同`
2. 一个属性出现 `两次` 且 `值不同`

像下面这样使用将会 `提示警告`：

```css

/* properties with the same value */
.mybox {
    border: 1px solid black;
    border: 1px solid black;
}

/* properties separated by another property */
.mybox {
    border: 1px solid black;
    color: green;
    border: 1px solid red;
}
```

像下面这样使用则不会 `提示警告`：

```css

/* one after another with different values */
.mybox {
    border: 1px solid black;
    border: 1px solid red;
}
```
