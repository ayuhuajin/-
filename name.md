#一般规范(文件规范)

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
> * 文件名要全部小写,多个单词可以用下划线 ( _ ) 或连字符 (-)连接,依据项目约定而定.

### 文件命名示例
> * 项目命名
全部采用小写方式,以下划线分隔。
例：project_name
> * 目录命名
全部采用小写方式,以下划线分隔。
有复数结构时，要采用复数命名法。
例：images, data_module
> * JS文件命名
全部采用小写方式,以下划线分隔。
例：demo_rem.js
> * CSS, SCSS文件命名
全部采用小写方式,以下划线分隔。
例：reset_common.scss
> * HTML文件命名
全部采用小写方式,以下划线分隔。
例：index_list.html

### [注释规范](http://www.jianshu.com/p/822aa0077595)
> * 单行注释 ( // )
单独一行：//(双斜线)与注释文字之间保留一个空格
在代码后面添加注释：//(双斜线)与代码之间保留一个空格，并且//(双斜线)与注释文字之间保留一个空格。
注释代码：//(双斜线)与代码之间保留一个空格。
```js
推荐 :
// 调用了一个函数；1)单独在一行
setTitle();

var maxCount = 10; // 设置最大量；2)在代码后面注释

// setName(); // 3)注释代码
```
> * 多行注释 ( / 注释说明 / )
若开始(/*和结束(*/)都在一行，推荐采用单行注释
若至少三行注释时，第一行为/*，最后行为*/，其他行以*开始，并且注释文字与*保留一个空格。
```
/*
* 代码执行到这里后会调用setTitle()函数
* setTitle()：设置title的值
*/
setTitle();
```
> * 函数 ( 方法 ) 注释

函数(方法)注释也是多行注释的一种，但是包含了特殊的注释要求，参照 [javadoc(百度百科)](https://baike.baidu.com/item/javadoc)
语法：
```js
/** 
* 函数说明 
* @关键字 
*/
```
### 代码检查
> * 对于比较宽松自由的编程语言来说，严格遵循编码规范和格式化风格指南就显得极为重要。遵循规范固然很好，但是有自动化流程来确保其执行情况，岂不更佳。Trust is good, control is better. 对于 JavaScript，建议使用 JSLint 或 JSHint。
### 驼峰式命名法介绍
> * 大驼峰式命名法(Pascal Case):首字母大写。
例:MyProject , SimBa
> * 小驼峰式命名法(Camel Case):首字母小写。
例:myProject , simBa


## github项目


* [github](https://github.com/ayuhuajin/) 

## 关于作者

```javascript
  var wsinghai = {
    nickName  : "wsinghai",
    site : "http://wsinghai.com"
  }
```
## 有问题反馈
在使用中有任何问题，欢迎反馈给我，可以用以下联系方式跟我交流
* 邮件(455493143@qq.com)
* QQ: 455493143

参考
1.[腾讯alloyteam团队前端代码规范](https://www.kancloud.cn/digest/code-guide/42603)
2.[小小倩](https://juejin.im/post/592d4a5b0ce463006b43b6da)
3.[前端编码规范](http://www.css88.com/archives/5505)
4.[百度前端](https://github.com/fex-team/styleguide)



