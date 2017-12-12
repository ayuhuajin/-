#HTML规范
本文档的目标是使HTML代码风格保持一致，容易被理解和被维护。
## 语法
> * 缩进使用soft tab（4个空格）；
> * 嵌套的节点应该缩进；
> * 在属性上，使用双引号，不要使用单引号；
> * 非特殊情况下CSS样式文件外链至HEAD之间，JAVASCRIPT文件外链至页面底部
> * 使用语义化标签，避免自定义标签
> * [建议] 每行不得超过 `120` 个字符。
> * [强制] `class` 必须单词全字母小写，单词间以 `-` 分隔。
> * 禁止为了 `hook 脚本`，创建无样式信息的 `class`。
> * [强制] `class` 必须代表相应模块或部件的内容或功能，不得以样式信息进行命名。
```html
<!-- good -->
<div class="sidebar"></div>

<!-- bad -->
<div class="left"></div>
```
## HTML5 doctype

> * 在页面开头使用这个简单地doctype来启用标准模式，使其在每个浏览器中尽可能一致的展现；建议使用大写的 `DOCTYPE`
> * DOCTYPE标签是一种标准通用标记语言的文档类型声明，它的目的是要告诉标准通用标记语言解析器，它应该使用什么样的文档类型定义（DTD）来解析文档。
使用文档声明类型的作用是为了防止开启浏览器的怪异模式。 
没有DOCTYPE文档类型声明会开启浏览器的怪异模式，浏览器会按照自己的解析方式渲染页面，在不同的浏览器下面会有不同的样式。
如果你的页面添加了<!DOCTYP>那么，那么就等同于开启了标准模式。浏览器会按照W3C标准解析渲染页面。

```html
<!DOCTYPE html>
<html>
    ...
</html>
```
## lang属性
> * 根据HTML5规范：
应在html标签上加上lang属性。这会给语音工具和翻译工具帮助，告诉它们应当怎么去发音和翻译。
更多关于 lang 属性的说明在这里；
在sitepoint上可以查到语言列表；
但sitepoint只是给出了语言的大类，例如中文只给出了zh，但是没有区分香港，台湾，大陆。而微软给出了一份更加详细的语言列表，其中细分了zh-cn, zh-hk, zh-tw。
```html
<!DOCTYPE html>
<html lang="zh-CN">
    ...
</html>
```
## 字符编码
> * 通过声明一个明确的字符编码，让浏览器轻松、快速的确定适合网页内容的渲染方式，通常指定为'UTF-8'。
```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
    </head>
    ...
</html>
```
## IE兼容模式
> * 用 `` 标签可以指定页面应该用什么版本的IE来渲染；

> * 如果你想要了解更多，请点击这里；
不同doctype在不同浏览器下会触发不同的渲染模式（这篇文章总结的很到位）。
```html
<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="X-UA-Compatible" content="IE=Edge">
    </head>
    ...
</html>
```
## 属性顺序
> * 属性应该按照特定的顺序出现以保证易读性；
```html
class
id
name
data-*
src, for, type, href, value , max-length, max, min, pattern
placeholder, title, alt
aria-*, role
required, readonly, disabled
class是为高可复用组件设计的，所以应处在第一位；

id更加具体且应该尽量少使用，所以将它放在第二位。
```

```html
<a class="..." id="..." data-modal="toggle" href="#">Example link</a>

<input class="form-control" type="text">

<img src="..." alt="...">
```
## 减少标签数量
> * 在编写HTML代码时，需要尽量避免多余的父节点；

> * 很多时候，需要通过迭代和重构来使HTML变得更少。
```html
<!-- Not well -->
<span class="avatar">
    <img src="...">
</span>
<!-- Better -->
<img class="avatar" src="...">
```
## 语义化
> * 根据元素（有时被错误地称作“标签”）其被创造出来时的初始意义来使用它。打个比方，用 heading 元素来定义头部标题，p 元素来定义文字段落，用 a 元素来定义链接锚点，等等。
```html
<!DOCTYPE html>
<html>
    <body>
        <header>
            <nav></nav>
        </header>
    </body>
</html>
```

## HTML 引号

> * 使用双引号(“”) 而不是单引号(”) 。

```html
不推荐
html 代码:
<div class='news-article'></div>

推荐
html 代码:
<div class="news-article"></div>
```

###[强制] 标签使用必须符合标签嵌套规则。

解释：

比如 div 不得置于 p 中，tbody 必须置于 table 中。

详细的标签嵌套规则参见[HTML DTD](http://www.cs.tut.fi/~jkorpela/html5.dtd)中的 `Elements` 定义部分。


#### [建议] `HTML` 标签的使用应该遵循标签的语义。

解释：

下面是常见标签语义

- p - 段落
- h1,h2,h3,h4,h5,h6 - 层级标题
- strong,em - 强调
- ins - 插入
- del - 删除
- abbr - 缩写
- code - 代码标识
- cite - 引述来源作品的标题
- q - 引用
- blockquote - 一段或长篇引用
- ul - 无序列表
- ol - 有序列表
- dl,dt,dd - 定义列表


示例：

```html
<!-- good -->
<p>Esprima serves as an important <strong>building block</strong> for some JavaScript language tools.</p>

<!-- bad -->
<div>Esprima serves as an important <span class="strong">building block</span> for some JavaScript language tools.</div>
```


#### [建议] 在 `CSS` 可以实现相同需求的情况下不得使用表格进行布局。

解释：

在兼容性允许的情况下应尽量保持语义正确性。对网格对齐和拉伸性有严格要求的场景允许例外，如多列复杂表单。


#### [建议] 标签的使用应尽量简洁，减少不必要的标签。

示例：

```html
<!-- good -->
<img class="avatar" src="image.png">

<!-- bad -->
<span class="avatar">
    <img src="image.png">
</span>
```
#### [建议] 自定义属性建议以 `xxx-` 为前缀，推荐使用 `data-`。

解释：

使用前缀有助于区分自定义属性和标准定义的属性。


示例：

```html
<ol data-ui-type="Select"></ol>
```

#### [建议] 标签的使用应尽量简洁，减少不必要的标签。

示例：

```html
<!-- good -->
<img class="avatar" src="image.png">

<!-- bad -->
<span class="avatar">
    <img src="image.png">
</span>
```

#### [建议] 启用 IE Edge 模式。

示例：

```html
<meta http-equiv="X-UA-Compatible" content="IE=Edge">
```

#### [强制] 保证 `favicon` 可访问。

解释：

在未指定 favicon 时，大多数浏览器会请求 Web Server 根目录下的 favicon.ico 。为了保证favicon可访问，避免404，必须遵循以下两种方法之一：

1. 在 Web Server 根目录放置 favicon.ico 文件。
2. 使用 link 指定 favicon。

#### [建议] 避免为 `img` 添加不必要的 `title` 属性。

解释：  

多余的 title 影响看图体验，并且增加了页面尺寸。

#### [建议] 为重要图片添加 `alt` 属性。

解释：

可以提高图片加载失败时的用户体验。
#### [建议] 添加 `width` 和 `height` 属性，以避免页面抖动。

#### [建议] 有下载需求的图片采用 `img` 标签实现，无下载需求的图片采用 `CSS` 背景图实现。
1. 产品 logo、用户头像、用户产生的图片等有潜在下载需求的图片，以 img 形式实现，能方便用户下载。
2. 无下载需求的图片，比如：icon、背景、代码使用的图片等，尽可能采用 css 背景图实现。

