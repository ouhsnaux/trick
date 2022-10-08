# ElementUI 图标乱码

## 原因

element UI内部使用 `node-sass` 编译，项目中一般使用更现代化的 `dart-sass` 处理。

`dart-sass` 在处理 `element UI` 中 `unicode` 图标时，将其转化为双字节字符，导致无法正常显示。

## 解决

### 添加 webpack 规则

在处理scss文件时将双字节字符转化为unicode

### 添加 css 文件

添加 css 文件，将图标样式复制一份，并提高样式特异性，比如在选择器前添加 body
然后再html中引入css文件
