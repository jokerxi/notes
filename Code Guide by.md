<conter>腾讯代码规范</conter>
=============

命名规则
-------------
1. [项目命名]<br>

> 栗子：my_project_name

2. [目录命名 有复数结构时，要采用复数命名法]<br>

> 栗子：scripts，styles，images,data_models

3. [JS文件命名 参照项目命名规则]<br>

> 栗子：account_model.js

4. [CSS,SCSS文件命名 参照项目命名规则]<br>

> 栗子：retina_sprites.scss</font>

5. [HTML文件命名 参照项目命名规则]<br>

> 栗子：error_report.html

HTML
-------------
<ul>
    <li>缩进使用soft tab(4个空格)；</li>
    <li>嵌套的节点应该缩进；</li>
    <li>在属性上，使用双引号，不要使用单引号；</li>
    <li>属性名全小写，用中划线做分隔符；</li>
    <li>不要在自动闭合标签结尾处使用斜线(<a href="https://dev.w3.org/html5/spec-author-view/syntax.html#syntax-start-tag">HTML5 规范</a>规范 指出他们是可选的)；</li>
</ul>
栗子：
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