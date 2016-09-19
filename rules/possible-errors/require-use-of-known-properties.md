# 使用规范中定义的属性
### Require use of known properties

`CSS` 的属性增加速度越来越快了，但是我们有时候不小心会写错属性，导致出现的错误。

## 规则描述

规则配置项: `known-properties`

该规则会检查所有的 `属性`，并判断该属性是不是 `CSS规范中支持的` 或 `是否拼写错误`，并且给出提示和警报。

对于厂商选择器（以 `-` 开始）是被忽略的，因为每个厂商会添加一些他们专属的属性，如果对每个浏览器的专属的属性都做判断的话，是一个非常大的工程量。

对于属性值也会做一些基本的检查，但并不是所有的属性值都能被检查到。因为属性值的范围太大，如果所有的属性值都做判断一个非常大的工程量。

像下面这样使用将会 `提示警告`：

```css

/* clr isn't a known property */
a {
    clr: red;
}

/* 'foo' isn't a valid color */
a {
    color: foo;
}
```

像下面这样使用则不会 `提示警告`：

```css
/* -moz- is a vendor prefix, so ignore */
a {
    -moz-foo: bar;
}
```
