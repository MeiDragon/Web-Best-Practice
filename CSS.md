# CSS
## 语法层面
### 声明以`;`为结尾
```css
.box {
  /* bad */
  height: 100px
  /* good */
  width: 100px;
}
```
### 使用 2 个空格替代 Tab
### 选择器名与`{`之间保留空格
```css
/* bad */
.box{}
/* good */
.box {}
```
### 属性名与`:`间无空格，`:`与属性值间有空格
```css
.box {
  /* bad */
  width :100px;
  /* good */
  height: 100px;
}
```
### 组合选择器 `> + ~ ||` 之间保留空格
```css
/* bad */
ul >li {}
/* good */
ul > li {}
```
### 多属性值各属性值间保留空格
```css
.box {
  /* bad */
  color: rgba(0,0,0,0);
  /* good */
  colorL rgba(0, 0, 0, 0);
}
```
### 注释规范
```css
/* bad */

/* comment*/
/*  comment  */
/* 
 *comment
 */

/* good */

/* comment */
/* 
 * comment
 */
```
### `}`单独成行
```css
/* bad */
.box {
  color: red;}
.box { color: red; }
/* good */
.box {
  color: red;
}
```
### 多选择器写法
```css
.a,
.b,
.c {
  color: red;
}
```
### 不推荐使用 id 选择器
后续难以进行样式覆盖
### 属性-值选择器值始终以`"`包裹
```css
/* bad */
.input[type=text] {

}
/* good */
.input[type="text"] {

}
```
### 十六进制小写易读
```css
/* bad */
.box {
  color: #ABFEDD;
}
/* good */
.box {
  color: #abfedd;
}
```
### 长度值为0时单位可省略
```css
/* bad */
.box {
  width: 0px;
}
/* good */
.box {
  width: 0;
}
```
### 不使用`@import`引入样式
```html
<style>
  /* bad */
  @import url("xxx.css");
</style>
<!-- good -->
<link rel="stylesheet" href="xxx.css" />
<!-- 或 sass/less 编译 -->
```
## 预处理器
### 运算符前后留空格
```css
/* bad */
.box {
  width: $default-width/ 2;
}
/* good */
.box {
  width: $default-width / 2;
}
```
## 格式化工具
### stylelint