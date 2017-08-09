# ESlint入门

```html
http://eslint.org/docs/developer-guide/
```

* rules代表规则，js语法会受到下面的规则影响：

```json
"rules": {
    // unix换行符(检查是否使用unix换行符)
    "linebreak-style": ["error", "unix"],
    // 分号党(检查是否以分号结尾)
    "semi": ["error", "always"],
    // 字符串单引号(检查字符串以单引号标识)
    "quotes": ["error", "single"],
    // 全等号(只做等值检查，不做类型转换)
    "eqeqeq": ["error", "always"],
    // tab缩进(检查是否tab缩进)
    "indent": ["error", "tab"],
}
```