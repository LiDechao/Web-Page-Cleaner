# ScrapBookPageCleaner
####`Greasemonkey`插件
####设置
点击Greasemonkey图标 -> Greasemonkey选项 -> 新建脚本模板（粘贴入下面代码）
```
// ==UserScript==
// @name        %name%
// @namespace   %namespace%
// @description %description%
// @include     %include%
// @exclude     %exclude%
// @version     1
// @grant       GM_log
// @require     https://code.jquery.com/jquery-1.7.2.min.js
// @require     https://raw.githubusercontent.com/webpatch/ScrapBookPageCleaner/master/comm.js
// ==/UserScript==

// 需要提取内容容器的css选择器
// 如 ".article"
let holdTag = ""

// 需要删除的容器的css选择器
let removeTags = [
  
];

// 需要注入的自定义css代码
// /* 及 */ 不可删除
let css = function(){  
/* 
  
*/
};

// 开始注入
setup();
```
####新建脚本
点击Greasemonkey图标 -> 新建用户脚本

填入名称

修改“脚本应用到”，可使用通配符`*`，及正则表达式

####修改脚本

变量说明：

|变量|变量类型|说明|
|:-:|:-:|:-:|
|`holdTag`|字符串类型|需要提取内容的容器选择器|
|`removeTags`|字符串数组|需要删除的容器选择器|
|`css`|多行文本|自定义的css文本，注意不能删除`/* */`注释符|

> 以上选择器都基于jQuery

例子：
```
let holdTag = ".article"
let removeTags = [
  ".footer",
  "#nav"
];
let css = function(){  
/* 
  .article{padding:0;margin:0;background-color:#fff;}
  .post{width:auto;}
*/
};
```
保存，然后刷新当前网页
