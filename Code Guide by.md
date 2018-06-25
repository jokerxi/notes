#<center>腾讯前端代码规范</center>
##<center>命名规则</center>
1. 项目命名<br>

    ><font color="#0000FF">栗子：</font>my_project_name

2. 目录命名 有复数结构时，要采用复数命名法<br>

    ><font color="#0000FF">栗子：</font>scripts，styles，images,data_models

3. JS文件命名 参照项目命名规则<br>

    ><font color="#0000ff">栗子：</font>account_model.js

4. CSS,SCSS文件命名 参照项目命名规则<br>

    ><font color="#0000ff">栗子：</font>retina_sprites.scss

5. HTML文件命名 参照项目命名规则<br>

    ><font color="#0000ff">栗子：</font>error_report.html

##<center>HTML</center>
###语法：
<ul>
    <li>缩进使用soft tab(4个空格)；</li>
    <li>嵌套的节点应该缩进；</li>
    <li>在属性上，使用双引号，不要使用单引号；</li>
    <li>属性名全小写，用中划线做分隔符；</li>
    <li>不要在自动闭合标签结尾处使用斜线(<a href="https://dev.w3.org/html5/spec-author-view/syntax.html#syntax-start-tag">HTML5 规范</a> 指出他们是可选的)；</li>
    <li>不要忽略可选的关闭标签，``<font color="#0000FF">栗子：</font></li> 和 </body>。```</li>
</ul>

><font color="#0000FF">栗子:</font>

``` html
<!DOCTYPE html>
<html>
    <head>
        <title>Page title</title>
    </head>
    <body>
        <img src="images/company_logo.png" alt="Company">

        <h1 class="hello-world">Hello, world!</h1>
    </body>
</html>
```

###HTML5 doctype
在页面开头使用这个简单地doctype来启用标准模式，使其在每个浏览器中尽可能一致的展现；<br>
虽然doctype不区分大小写，但是按照惯例，doctype大写<a href="https://stackoverflow.com/questions/15594877/is-there-any-benefits-to-use-uppercase-or-lowercase-letters-with-html5-tagname">( 关于html属性，大写还是小写。)</a>

><font color="#0000FF">栗子:</font>

``` html
<!DOCTYPE html>
<html>
  ···
</html>
```

###lang属性
根据HTML5规范：
>应在html标签上加上lang属性。这会给语音工具和翻译工具帮助，告诉它们应当怎么去发音和翻译。

<ul>
    <li>更多关于 lang 属性的说明<a href="http://w3c.github.io/html/semantics.html#the-html-element">在这里</a>；</li>
    <li>在sitepoint上可以查到<a href="http://reference.sitepoint.com/html/lang-codes">语言列表</a>；<br></li>
    <li>但sitepoint只是给出了语言的大类，例如中文只给出了zh，但是没有区分香港，台湾，大陆。而微软给出了一份更加<a href="http://msdn.microsoft.com/en-us/library/ms533052(v=vs.85).aspx">详细的语言列表</a>，其中细分了zh-cn, zh-hk, zh-tw。</li>
</ul>
><font color="#0000FF">栗子：</font>

```html
<!DOCTYPE html>
<html lang="en-us">
    ...
</html>
```

###字符编码
通过声明一个明确的字符编码，让浏览器轻松、快速的确定适合网页内容的渲染方式，通常指定为'UTF-8'。

><font color="#0000FF">栗子：</font>

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
    </head>
    ...
</html>
```

###IE兼容模式
<ul>
    <li>用 <font color="red">```<meta>```</font>标签可以指定页面应该用什么版本的IE来渲染；</li>
    <li>如果你想要了解更多，请点击<a href="https://stackoverflow.com/questions/6771258/what-does-meta-http-equiv-x-ua-compatible-content-ie-edge-do">这里</a>；</li>
    <li>不同doctype在不同浏览器下会触发不同的渲染模式（<a href="https://hsivonen.fi/doctype/">这篇文章</a>总结的很到位）。</li>
</ul>
><font color="#00f">栗子：</font>

``` html
<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="X-UA-Compatible" content="IE=Edge">
    </head>
    ...
</html>
```

###引入CSS，JS
根据HTML5规范, 通常在引入CSS和JS时不需要指明 <font color="#f00">```type```</font>，因为 <font color="#f00">```text/css```</font> 和 <font color="#f00">```text/javascript```</font> 分别是他们的默认值。
<h4>HTML5规范链接:</h4>
<ul>
    <li><a href="https://www.w3.org/TR/2011/WD-html5-20110525/semantics.html#the-link-element">使用link</a></li>
    <li><a href="https://www.w3.org/TR/2011/WD-html5-20110525/semantics.html#the-style-element">使用style</a></li>
    <li><a href="https://www.w3.org/TR/2011/WD-html5-20110525/scripting-1.html#the-script-element">使用script</a></li>
</ul>

>栗子：

``` html
<!-- External CSS -->
<link rel="stylesheet" href="code_guide.css">

<!-- In-document CSS -->
<style>
    ...
</style>

<!-- External JS -->
<script src="code_guide.js"></script>

<!-- In-document JS -->
<script>
    ...
</script>
```

###属性顺序
属性应该按照特定的顺序出现以保证易读性；
<ul>
    <li><font color="#f00">```class```</font></li>
    <li><font color="#f00">```id```</font></li>
    <li><font color="#f00">```name```</font></li>
    <li><font color="#f00">```data-*```</font></li>
    <li><font color="#f00">```src, for, type, href, value , max-length, max, min, pattern```</font></li>
    <li><font color="#f00">```placeholder, title, alt```</font></li>
    <li><font color="#f00">```aria-*, role```</font></li>
    <li><font color="#f00">```required, readonly, disabled```</font></li>
</ul>
class是为高可复用组件设计的，所以应处在第一位；<br>
id更加具体且应该尽量少使用，所以将它放在第二位。

>栗子：

``` html
<a class="..." id="..." data-modal="toggle" href="#">Example link</a>

<input class="form-control" type="text">

<img src="..." alt="...">
```

###boolean属性
>boolean属性的存在表示取值为true，不存在则表示取值为false.

<ul>
    <li>boolean属性指不需要声明取值的属性，XHTML需要每个属性声明取值，但是HTML5并不需要；</li>
    <li>更多内容可以参考 <a href="https://html.spec.whatwg.org/multipage/common-microsyntaxes.html#boolean-attributes">WhatWG section on boolean attributes：</a></li>
</ul>

>栗子：

``` html
<input type="text" disabled>

<input type="checkbox" value="1" checked>

<select>
    <option value="1" selected>1</option>
</select>
```

### JS生成标签
在JS文件中生成标签让内容变得更难查找，更难编辑，性能更差。应该尽量避免这种情况的出现。

###减少标签数量
在编写HTML代码时，需要尽量避免多余的父节点；<br>
很多时候，需要通过迭代和重构来使HTML变得更少。

>栗子：

``` html
<!-- Not well -->
<span class="avatar">
    <img src="...">
</span>

<!-- Better -->
<img class="avatar" src="...">
```
###实用高于完美
尽量遵循HTML标准和语义，但是不应该以浪费实用性作为代价；<br>
任何时候都要用尽量小的复杂度和尽量少的标签来解决问题。
<div style="height: 1rem"></div>

##<center><font>CSS, SCSS</font></center>
###缩进
使用soft tab（4个空格）。

>栗子：

``` css
.element {
    position: absolute;
    top: 10px;
    left: 10px;

    border-radius: 10px;
    width: 50px;
    height: 50px;
}
```

###分号
每个属性声明末尾都要加分号。

>栗子：

``` css
.element {
    width: 20px;
    height: 20px;

    background-color: red;
}
```

###空格
以下几种情况不需要空格：
<ul>
    <li>属性名后</li>
    <li>多个规则的分隔符','前</li>
    <li><font color="#f00">```!important```</font> '!'后</li>
    <li>属性值中'('后和')'前</li>
    <li>行末不要有多余的空格</li>
</ul>

以下几种情况需要空格：
<ul>
    <li>属性值前</li>
    <li>选择器'>', '+', '~'前后</li>
    <li>'{'前</li>
    <li><font color="#f00">```!important```</font> '!'前</li>
    <li><font color="#f00">```@else```</font> 前后</li>
    <li>属性值中的','后</li>
    <li>注释'/*'后和'*/'前</li>
</ul>

>栗子：

``` css
/* not good */
.element {
    color :red! important;
    background-color: rgba(0,0,0,.5);
}

/* good */
.element {
    color: red !important;
    background-color: rgba(0, 0, 0, .5);
}

/* not good */
.element ,
.dialog{
    ...
}

/* good */
.element,
.dialog {

}

/* not good */
.element>.dialog{
    ...
}

/* good */
.element > .dialog{
    ...
}

/* not good */
.element{
    ...
}

/* good */
.element {
    ...
}

/* not good */
@if{
    ...
}@else{
    ...
}

/* good */
@if {
    ...
} @else {
    ...
}
```

###空行
以下几种情况需要空行：
<ul>
    <li>文件最后保留一个空行</li>
    <li>'}'后最好跟一个空行，包括scss中嵌套的规则</li>
    <li>属性之间需要适当的空行，具体见<a href="http://alloyteam.github.io/CodeGuide/#css-declaration-order">属性声明顺序</a></li>
</ul>

>栗子：

``` css
/* not good */
.element {
    ...
}
.dialog {
    color: red;
    &:after {
        ...
    }
}

/* good */
.element {
    ...
}

.dialog {
    color: red;

    &:after {
        ...
    }
}
```

###换行
以下几种情况不需要换行：
<ul>
    <li>'{'前</li>
</ul>
以下几种情况需要换行：
<ul>
    <li>'{'后和'}'前</li>
    <li>每个属性独占一行</li>
    <li>多个规则的分隔符','后</li>
</ul>

>栗子：

``` css
/* not good */
.element
{color: red; background-color: black;}

/* good */
.element {
    color: red;
    background-color: black;
}

/* not good */
.element, .dialog {
    ...
}

/* good */
.element,
.dialog {
    ...
}
```

###注释
<ul>
    <li>注释统一用'/* */'（scss中也不要用'//'），具体参照右边的写法；</li>
    <li>缩进与下一行代码保持一致；</li>
    <li>可位于一个代码行的末尾，与代码间隔一个空格。</li>
</ul>

>栗子：

``` css
/* Modal header */
.modal-header {
    ...
}

/*
 * Modal header
 */
.modal-header {
    ...
}

.modal-header {
    /* 50px */
    width: 50px;

    color: red; /* color red */
}
```

###引号
<ul>
    <li>最外层统一使用双引号；</li>
    <li>url的内容要用引号；</li>
    <li>属性选择器中的属性值需要引号。</li>
</ul>

>栗子：

``` css
.element:after {
    content: "";
    background-image: url("logo.png");
}

li[data-type="single"] {
    ...
}
```

###命名
<ul>
    <li>类名使用小写字母，以中划线分隔</li>
    <li>id采用驼峰式命名</li>
    <li>scss中的变量、函数、混合、placeholder采用驼峰式命名</li>
</ul>

>栗子：

``` css
/* class */
.element-content {
    ...
}

/* id */
#myDialog {
    ...
}

/* 变量 */
$colorBlack: #000;

/* 函数 */
@function pxToRem($px) {
    ...
}

/* 混合 */
@mixin centerBlock {
    ...
}

/* placeholder */
%myDialog {
    ...
}
```

###属性声明顺序
相关的属性声明按右边的顺序做分组处理，组之间需要有一个空行。

>栗子：

``` css
.declaration-order {
    display: block;
    float: right;

    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: 100;

    border: 1px solid #e5e5e5;
    border-radius: 3px;
    width: 100px;
    height: 100px;

    font: normal 13px "Helvetica Neue", sans-serif;
    line-height: 1.5;
    text-align: center;

    color: #333;
    background-color: #f5f5f5;

    opacity: 1;
}

/* 下面是推荐的属性的顺序 */
[
    [
        "display",
        "visibility",
        "float",
        "clear",
        "overflow",
        "overflow-x",
        "overflow-y",
        "clip",
        "zoom"
    ],
    [
        "table-layout",
        "empty-cells",
        "caption-side",
        "border-spacing",
        "border-collapse",
        "list-style",
        "list-style-position",
        "list-style-type",
        "list-style-image"
    ],
    [
        "-webkit-box-orient",
        "-webkit-box-direction",
        "-webkit-box-decoration-break",
        "-webkit-box-pack",
        "-webkit-box-align",
        "-webkit-box-flex"
    ],
    [
        "position",
        "top",
        "right",
        "bottom",
        "left",
        "z-index"
    ],
    [
        "margin",
        "margin-top",
        "margin-right",
        "margin-bottom",
        "margin-left",
        "-webkit-box-sizing",
        "-moz-box-sizing",
        "box-sizing",
        "border",
        "border-width",
        "border-style",
        "border-color",
        "border-top",
        "border-top-width",
        "border-top-style",
        "border-top-color",
        "border-right",
        "border-right-width",
        "border-right-style",
        "border-right-color",
        "border-bottom",
        "border-bottom-width",
        "border-bottom-style",
        "border-bottom-color",
        "border-left",
        "border-left-width",
        "border-left-style",
        "border-left-color",
        "-webkit-border-radius",
        "-moz-border-radius",
        "border-radius",
        "-webkit-border-top-left-radius",
        "-moz-border-radius-topleft",
        "border-top-left-radius",
        "-webkit-border-top-right-radius",
        "-moz-border-radius-topright",
        "border-top-right-radius",
        "-webkit-border-bottom-right-radius",
        "-moz-border-radius-bottomright",
        "border-bottom-right-radius",
        "-webkit-border-bottom-left-radius",
        "-moz-border-radius-bottomleft",
        "border-bottom-left-radius",
        "-webkit-border-image",
        "-moz-border-image",
        "-o-border-image",
        "border-image",
        "-webkit-border-image-source",
        "-moz-border-image-source",
        "-o-border-image-source",
        "border-image-source",
        "-webkit-border-image-slice",
        "-moz-border-image-slice",
        "-o-border-image-slice",
        "border-image-slice",
        "-webkit-border-image-width",
        "-moz-border-image-width",
        "-o-border-image-width",
        "border-image-width",
        "-webkit-border-image-outset",
        "-moz-border-image-outset",
        "-o-border-image-outset",
        "border-image-outset",
        "-webkit-border-image-repeat",
        "-moz-border-image-repeat",
        "-o-border-image-repeat",
        "border-image-repeat",
        "padding",
        "padding-top",
        "padding-right",
        "padding-bottom",
        "padding-left",
        "width",
        "min-width",
        "max-width",
        "height",
        "min-height",
        "max-height"
    ],
    [
        "font",
        "font-family",
        "font-size",
        "font-weight",
        "font-style",
        "font-variant",
        "font-size-adjust",
        "font-stretch",
        "font-effect",
        "font-emphasize",
        "font-emphasize-position",
        "font-emphasize-style",
        "font-smooth",
        "line-height",
        "text-align",
        "-webkit-text-align-last",
        "-moz-text-align-last",
        "-ms-text-align-last",
        "text-align-last",
        "vertical-align",
        "white-space",
        "text-decoration",
        "text-emphasis",
        "text-emphasis-color",
        "text-emphasis-style",
        "text-emphasis-position",
        "text-indent",
        "-ms-text-justify",
        "text-justify",
        "letter-spacing",
        "word-spacing",
        "-ms-writing-mode",
        "text-outline",
        "text-transform",
        "text-wrap",
        "-ms-text-overflow",
        "text-overflow",
        "text-overflow-ellipsis",
        "text-overflow-mode",
        "-ms-word-wrap",
        "word-wrap",
        "-ms-word-break",
        "word-break"
    ],
    [
        "color",
        "background",
        "filter:progid:DXImageTransform.Microsoft.AlphaImageLoader",
        "background-color",
        "background-image",
        "background-repeat",
        "background-attachment",
        "background-position",
        "-ms-background-position-x",
        "background-position-x",
        "-ms-background-position-y",
        "background-position-y",
        "-webkit-background-clip",
        "-moz-background-clip",
        "background-clip",
        "background-origin",
        "-webkit-background-size",
        "-moz-background-size",
        "-o-background-size",
        "background-size"
    ],
    [
        "outline",
        "outline-width",
        "outline-style",
        "outline-color",
        "outline-offset",
        "opacity",
        "filter:progid:DXImageTransform.Microsoft.Alpha(Opacity",
        "-ms-filter:\\'progid:DXImageTransform.Microsoft.Alpha",
        "-ms-interpolation-mode",
        "-webkit-box-shadow",
        "-moz-box-shadow",
        "box-shadow",
        "filter:progid:DXImageTransform.Microsoft.gradient",
        "-ms-filter:\\'progid:DXImageTransform.Microsoft.gradient",
        "text-shadow"
    ],
    [
        "-webkit-transition",
        "-moz-transition",
        "-ms-transition",
        "-o-transition",
        "transition",
        "-webkit-transition-delay",
        "-moz-transition-delay",
        "-ms-transition-delay",
        "-o-transition-delay",
        "transition-delay",
        "-webkit-transition-timing-function",
        "-moz-transition-timing-function",
        "-ms-transition-timing-function",
        "-o-transition-timing-function",
        "transition-timing-function",
        "-webkit-transition-duration",
        "-moz-transition-duration",
        "-ms-transition-duration",
        "-o-transition-duration",
        "transition-duration",
        "-webkit-transition-property",
        "-moz-transition-property",
        "-ms-transition-property",
        "-o-transition-property",
        "transition-property",
        "-webkit-transform",
        "-moz-transform",
        "-ms-transform",
        "-o-transform",
        "transform",
        "-webkit-transform-origin",
        "-moz-transform-origin",
        "-ms-transform-origin",
        "-o-transform-origin",
        "transform-origin",
        "-webkit-animation",
        "-moz-animation",
        "-ms-animation",
        "-o-animation",
        "animation",
        "-webkit-animation-name",
        "-moz-animation-name",
        "-ms-animation-name",
        "-o-animation-name",
        "animation-name",
        "-webkit-animation-duration",
        "-moz-animation-duration",
        "-ms-animation-duration",
        "-o-animation-duration",
        "animation-duration",
        "-webkit-animation-play-state",
        "-moz-animation-play-state",
        "-ms-animation-play-state",
        "-o-animation-play-state",
        "animation-play-state",
        "-webkit-animation-timing-function",
        "-moz-animation-timing-function",
        "-ms-animation-timing-function",
        "-o-animation-timing-function",
        "animation-timing-function",
        "-webkit-animation-delay",
        "-moz-animation-delay",
        "-ms-animation-delay",
        "-o-animation-delay",
        "animation-delay",
        "-webkit-animation-iteration-count",
        "-moz-animation-iteration-count",
        "-ms-animation-iteration-count",
        "-o-animation-iteration-count",
        "animation-iteration-count",
        "-webkit-animation-direction",
        "-moz-animation-direction",
        "-ms-animation-direction",
        "-o-animation-direction",
        "animation-direction"
    ],
    [
        "content",
        "quotes",
        "counter-reset",
        "counter-increment",
        "resize",
        "cursor",
        "-webkit-user-select",
        "-moz-user-select",
        "-ms-user-select",
        "user-select",
        "nav-index",
        "nav-up",
        "nav-right",
        "nav-down",
        "nav-left",
        "-moz-tab-size",
        "-o-tab-size",
        "tab-size",
        "-webkit-hyphens",
        "-moz-hyphens",
        "hyphens",
        "pointer-events"
    ]
]
```