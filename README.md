### 通用
- [x] 文件编码采用**UTF-8**格式
- [x] 使用**4个空格**作为缩进
- [x] 所有语句必须以;结束
- [x] 所有需要上线的css、js必须压缩
- [x] 引入资源使用相对路径，不要指定资源所带的具体协议 ( http:,https: ) ，除非这两者协议都不可用。
- [x] 书写链接是，必须避免重定向，例如：href="http://gtadata.com/"，即需在URL地址后面加上"/";
- [x] 相对路径必须以./号开头

### 文件命名规则
> * 文件名不得含有空格
> * 文件名要全部小写,多个单词可以用下划线 ( _ ) 或连字符 (-)连接,依据项目约定而定

### html书写规则
> * alt标签不为空
> * 使用双引号("") 而不是单引号('') 。
> * 使用语义化标签，避免自定义标签.
> * `class` 必须单词全字母小写，单词间以 `-` 分隔。
> * 禁止为了 `hook 脚本`，创建无样式信息的 `class`。
> * `class` 必须代表相应模块或部件的内容或功能，不得以样式信息进行命名。
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
```

### css书写规则
> * 每个属性声明末尾都要加分号。
> * 类名使用小写字母，以中划线分隔
> * id采用驼峰式命名
> * 从结构、表现、行为分离的原则来看，应该尽量避免css中出现HTML标签，并且在css选择器中出现标签名会存在潜在的问题。
> * 如果你不写很通用的，需要匹配到DOM末端的选择器， 你应该总是考虑直接子选择器。
```
不推荐
css 代码:
.content .title {
  font-size: 2rem;
}
推荐

css 代码:
.content > .title {
  font-size: 2rem;
}
 
.content > .content-body > .title {
  font-size: 1.5rem;
}
 
.content > .content-body > .teaser > .title {
  font-size: 1.2rem;
}
```
> * scss中的变量、函数、混合、placeholder采用驼峰式命名
```css
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
> * css属性声明顺序
```css
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
```

##js书写规则
- [x] 变量命名规范
```js
s：表示字符串。例如：sName，sHtml;
n：表示数字。例如：nPage，nTotal;
b：表示逻辑。例如：bChecked，bHasLogin;
a：表示数组。例如：aList，aGroup;
r：表示正则表达式。例如：rDomain，rEmail;
f：表示函数。例如：fGetHtml，fInit;
o：表示以上未涉及到的其他对象，例如：oButton，oDate;
```
> * 函数命名
命名方式 : 小驼峰方式 ( 构造函数使用大驼峰命名法 )
命名规则 : 前缀为动词
can: 判断是否可执行某个动作 ( 权限 )   函数返回一个布尔值。true：可执行；false：不可执行
has: 判断是否含有某个值   函数返回一个布尔值。true：含有此值；false：不含有此值
is: 判断是否为某个值    函数返回一个布尔值。true：为某个值；false：不为某个值
get: 获取某个值      函数返回一个非布尔值
set: 设置某个值      无返回值、返回是否设置成功或者返回链式对象

```js
推荐：
//是否可阅读
function canRead(){
    return true;
}
//获取姓名
function getName{
    return this.name
}
```

> * 常量全大写，用下划线连接
命名方法 : 全部大写
命名规范 : 使用大写字母和下划线来组合命名，下划线用以分割单词。

```js
推荐：
 var MAX_COUNT = 10;
 var URL = 'http://www.baidu.com';
```
> * 私有属性、变量和方法以下划线 _ 开头
```js
var _oPrivateMethod = {};
var _this = $(this);
```