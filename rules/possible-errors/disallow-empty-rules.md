# 不允许选择器的内容为空
### Disallow empty rules

不允许选择器的内容为空，例如：

```css
.foo {
}
```

很多时候我们会忘记 `删除` 或者无意中 `添加` 了内容为空的选择器。去除这些选择器无疑能减少 `CSS` 代码体积。

## 规则描述

规则配置项: `empty-rules`

当代码中出现了内容为空的选择器，`CSSLint` 将会给出提示和警报。例如：

```css
.mybox { }

.mybox {

}

.mybox {
    /* a comment */
}
```
