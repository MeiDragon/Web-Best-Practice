# HTML
## 语法层面
### 显式标明标准类型文档
使得不同浏览器以标准语法解析文档
```html
<!doctype html>
<html>

</html>
```
### 建议标明语言
```html
<html lang="zh-CN">

</html>
```
### 显式指定字符编码
```html
<meta charset="utf-8" />
```
### 标签小写，包括 doctype
```html
<!-- bad -->
<DIV></DIV>
<!-- good -->
<div></div>
```
### 使用 2 个空格替代 Tab
软制表符能使得任意环境下代码呈现一致
### 标签属性上用双引号
```html
<!-- bad -->
<img src='xxx.webp' alt='xxx' />
<!-- good -->
<img src="xxx.webp" alt="xxx" />
```
### IE 兼容模式
针对 < IE10
```html
<meta http-equiv="x-ua-compatible" content="ie=edge">
```
### 外部 CSS JavaScript 引入
引入标签省略 `text/css`、`text/javascript`，因为这是默认属性
```html
<link ref="stylesheet" href="xxx.css" />
<script src="xxx.js"></script>
```
### 注重语义化标签的使用
```html
<!-- bad -->
<div class="btn" onClick="handleClick">点我</div>
<!-- good -->
<button>点我</button>
```
### 布尔属性为 true 时没必要给值
```html
<!-- bad -->
<input type="text" disabled="true">
<input type="checkbox" value="1" checked="true">
<!-- good -->
<input type="text" disabled>
<input type="checkbox" value="1" checked>
```
### 减少非必要标签嵌套
```html
<!-- bad -->
<span>
  <img />
</span>
<!-- good -->
<img />
```
### 样式、脚本书写位置
建议在 head 标签内写样式，body 标签尾引入脚本
```html
<!doctype html>
<html>
  <head>
    <link ref="stylesheet" href="xxx.css" />
    <style></style>
  </head>
  <body>
    <!-- ...省略 -->
    <script src="xxx.js"></script>
  </body>
</html>
```
### 页面标题有且只有一个
```html
<head>
  <title>xxx</title>
</head>
```
### 注重 Accessibility
网页可访问性能够在弱网、无障碍场景下发挥作用
```html
<!-- bad -->
<img src="xxx.webp" />
<!-- good -->
<img src="xxx.webp" alt="xxx" />
```
### class id 遵循 Kebab case 命名
```html
<!-- bad -->
<div class="litPig"></div>
<div class="LitPig"></div>
<!-- good -->
<div class="lit-pig"></div>
```
### 注释
```html
<!-- 单行注释 -->
<!-- 
  多行注释
  多行注释
-->
```
### 加速 DNS 解析
`pre-fetch` 只对跨域 dns 查询有效，因此应避免同域情况下使用
`preconnect` 包含 dns 预解析、TCP/TLS 连接工作，能进一步减少跨域请求感知延迟。应当谨慎使用，只对关键连接进行声明
```html
<link ref="preconnect" href="https://i0.hdslb.com/bfs/archive/" crossorigin />
<link ref="dns-prefetch" href="https://i0.hdslb.com/bfs/archive/" />
```
[MDN - dns-prefetch](https://developer.mozilla.org/en-US/docs/Web/Performance/dns-prefetch#best_practices)
### 预加载关键资源
谨慎使用，加载并缓存关键资源
```html
<!-- 字体文件按规定是匿名模式加载的，需要指定 crossorigin -->
<link
  rel="preload"
  href="fonts/cicle_fina-webfont.woff2"
  as="font"
  type="font/woff2"
  crossorigin />
```
[MDN - preload](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Attributes/rel/preload)
[MDN - crossorigin](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Attributes/crossorigin)
## IDE 设置
- 软制表符，使用 2 个空格代替 Tab；
- 设置 UTF-8 编码；
- 保存时去除多余空格；
- 文件行尾新增一行;
## 基本模板
```html
<!doctype html>
<html lang="zh-CN">
  <head>
    <meta charset="utf-8" />
    <title>xxx 标题</title>
    <!-- 略 -->
    <link rel="stylesheet" href="xxx.css" />
  </head>
  <body>
    <div id="test-box"></div>
    <!--
      略
      略
    -->
    <script src="xxx.js"></script>
  </body>
</html>
```