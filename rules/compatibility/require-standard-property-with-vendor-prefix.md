# 使用带有厂商标识的属性需带上标准属性
### Require standard property with vendor prefix

厂商标识的出现是为了在 `CSS` 标准未发布前实验一些新的 `CSS` 属性。它将允许浏览器和开发者去使用测试这个 `CSS` 属性在正式写入标准前 和 用于浏览器的兼容。当标准发布之后，`标准属性` 名通常是和 `厂商标识后的属性名` 一致，这是防止同一个功能出现多个属性名。

某一个属性在 `CSS` 标准发布后，浏览器将会去掉带有厂商标识的该属性，如果我们在使用带有厂商标识的属性带上标准属性，这样的话页面在新版本的浏览器中也能正常显示。例如：

```css
.mybox {
    -moz-border-radius: 5px;
    border-radius: 5px;
}
```

遵循这条规则将能保证我们书写的 `CSS` 代码能向后兼容（即向新版本的浏览器兼容），能减少我们未来因为不书写标准属性引起页面错误 和 不需要再花时间去去除厂商标识符。

## 规则描述

规则配置项: `vendor-prefix`

这条规则的目的是为了帮助我们在使用厂商标识符后检查是否书写了该标准属性。具体规则如下：

1. 一个带有厂商标识符的属性没有在它后面跟上标准属性
1. 标准属性写在带厂商标识的该属性前

像下面这样使用则会 `提示警报`：

```css

/* 缺少标准属性 */
.mybox {
    -moz-border-radius: 5px;
}

/* 标准属性应该排列在该厂商标识属性后 */
.mybox {
    border-radius: 5px;
    -webkit-border-radius: 5px;
}
```

像下面这样使用则不会 `提示警报`：

```css
/* 使用厂商标识符并在其后书写了标准属性 */
.mybox {
    -moz-border-radius: 5px;
    border-radius: 5px;
}
```

## 扩展阅读

* [Remember non-vendor-prefixed CSS 3 properties (and put them last) - 使用CSS3时记得使用标准属性](http://www.456bereastreet.com/archive/201009/remember_non-vendor-prefixed_css_3_properties_and_put_them_last/)
