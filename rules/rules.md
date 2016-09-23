# 规则
## Parsing errors should be fixed - 语法错误必须被修改
这条是最重要的规则，且在 `CSS Lint` 中不能被关闭。语法错误的原因可能是你少写了冒号、分号或者拼写错误。这将可能导致浏览器，丢弃这个属性或者丢弃这个选择器。

## Possible Errors - 可能潜在的错误

遵守这些规则将会 `预防` 可能潜在的错误。

* `box-model`: [Beware of box model size - 小心使用盒模型](./possible-errors/beware-of-box-model-size.md)
* `display-property-grouping`: [Require properties appropriate for display - 正确使用 display 相关属性](./possible-errors/require-properties-appropriate-for-display.md)
* `duplicate-properties`: [Disallow duplicate properties - 不允许属性重复](./possible-errors/disallow-duplicate-properties.md)
* `empty-rules`: [Disallow empty rules - 不允许选择器的内容为空](./possible-errors/disallow-empty-rules.md)
* `known-properties`: [Require use of known properties - 使用规范中定义的属性](./possible-errors/require-use-of-known-properties.md)

## Compatibility - 兼容性

遵守这些规则将会 `兼容` 更多的浏览器。(译者注：其实主要还是在针对IE6浏览器做兼容，如果不需要兼容IE6浏览器的话，规则配置项可以选择关闭)

* `adjoining-classes`: [Disallow adjoining classes - 不允许使用多类选择器](./compatibility/disallow-adjoining-classes.md)
* `box-sizing`: [Disallow box-sizing - 不允许使用 box-sizing 属性](./compatibility/disallow-box-sizing.md)
* `compatible-vendor-prefixes`: [Require compatible vendor prefixes - 添加厂商标识](./compatibility/require-compatible-vendor-prefixes.md)
* `gradients`: [Require all gradient definitions - 渐变色相关属性需要写完整](./compatibility/require-all-gradient-definitions.md)
* `text-indent`: [Disallow negative text-indent - 文本缩进实现隐藏效果时的小提示](./compatibility/disallow-negative-text-indent.md)
* `vendor-prefix`: [Require standard property with vendor prefix](./compatibility/require-standard-property-with-vendor-prefix.md)
* `fallback-colors`: [[Require fallback colors]]
* `star-property-hack`: [[Disallow star hack]]
* `underscore-property-hack`: [[Disallow underscore hack]]
* `bulletproof-font-face`: [[Bulletproof font-face]](new in v0.9.10)

## Performance

The following rules are aimed at improving CSS performance, including runtime performance and overall code size.

* `font-faces`: [[Don't use too many web fonts]]
* `import`: [[Disallow @import]]
* `regex-selectors`: [[Disallow selectors that look like regular expressions]]
* `universal-selector`: [[Disallow universal selector]]
* `unqualified-attributes`: [[Disallow unqualified attribute selectors]]
* `zero-units`: [[Disallow units for zero values]]
* `overqualified-elements`: [[Disallow overqualified elements]]
* `shorthand`: [[Require shorthand properties]]
* `duplicate-background-images`: [[Disallow duplicate background images]]

## Maintainability & Duplication

These rules help to ensure your code is readable and maintainable by others.

* `floats`: [[Disallow too many floats]]
* `font-sizes`: [[Don't use too many font-size declarations]]
* `ids`: [[Disallow IDs in selectors]]
* `important`: [[Disallow !important]]

## Accessibility

These rules are designed to pick out possible accessibility issues.

* `outline-none`: [[Disallow outline:none]]

## OOCSS

These rules are based on the principles of OOCSS.

* `qualified-headings`: [[Disallow qualified headings]]
* `unique-headings`: [[Headings should only be defined once]]

## Translation
* [Read this in Korean](https://github.com/hyunchulkwak/csslint/wiki/%EA%B7%9C%EC%B9%99)
