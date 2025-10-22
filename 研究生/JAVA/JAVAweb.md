## 前端
html负责网页的结构，css负责网页的表现，js负责网页的行为交互
https://developer.mozilla.org/en-US/ 前端文档网页
### HTML
*超文本标记语言*
超文本：可以定义文字，图片，视频等
标记语言：由标签构成的语言
```html
<html>

<head>

<title>html快速入门</title>

</head>

<body>

<h1>hello HTML</h1>

<img src="img/1.png">

</body>

</html>
```

超链接
```html
<!--  a 超链接标签
	href 链接地址，url
	target 打开方式
		_blank:新窗口打开
		_self:本窗口打开，默认

-->
<a href="http://www.cctv.com">央视网</a>
```


html标签
head标签：给浏览器看的，如css样式
body标签：给用户看的，如文字图片音频等

表题标签
```html
<h1>-<h6>
```




表单标签：form
```
<!-- form标签属性

action: 表单提交的地址

method: 表单提交方式

get: 表单提交方式为get

post: 表单提交方式为post

enctype: 表单编码类型

target: 表单提交目标

autocomplete: 表单自动完成

novalidate: 表单验证

name: 表单名称

注意：表单项如果想要提交数据，那么form标签的属性必须设置name属性

-->
```
![[Pasted image 20251016162654.png]]

表格标签：
![[Pasted image 20251016172535.png]]

### CSS
*层叠样式表*
flex布局
![[Pasted image 20251016172744.png]]

盒子模型
![[Pasted image 20251016154048.png]]
div（块）标签独占一行
span（行内块）标签一行可以多个
padding：内边距
border：边框
margin：外边距

### JS
JavaScript
#### js的核心语法
##### js引入方式
1. 内部脚本 ，js代码直接放在html代码中，一般放在body的底部
2. 外部脚本，定义在外部文件当中，然后引入到html中

```
<script>

//1. 内部脚本

alert('Hello JS');

</script>

  

<!-- 2. 外部脚本 -->

<script src="js/demo.js"></script>
```

##### 基础语法

常量&变量
用let关键字声明变量
用const声明常量
![[Pasted image 20251016175456.png]]

##### 数据类型
![[Pasted image 20251016175621.png]]
模版字符串
```
${变量名}
```

##### 核心语法
函数：用function定义函数，弱类型语言，形参和返回值不需要类型
匿名函数：函数表达式，箭头函数（不用function来定义函数）
![[Pasted image 20251016185555.png]]
总结：
![[Pasted image 20251016185821.png]]

自定义对象
![[Pasted image 20251016193647.png]]

json（js对象标记法书写的文本）
结构简单层次鲜明，多用于数据载体在网络中进行传输

```js
JSON.stringify(person) //js对象 --> json字符串
```

```js
let personJson = '{"name": "heima", "age": 18}';

alert(JSON.parse(personJson).name);

//json格式字符串转化成js对象，json格式外层要加单引号，里面的所有键和值都要用双引号包起来
```

##### DOM
文档对象模型，将标记语言的各个组成部分都封装成对象
![[Pasted image 20251016195444.png]]

操作步骤：
1. 获取DOM对象
		如何获取：
```
document.querySelect('选择器')
decument.querySelectAll('选择器')
```
2. 操作DOM对象
	看文档

#### 事件监听
![[Pasted image 20251016205931.png]]

四种事件
1. 鼠标事件
2. 键盘事件
3. 焦点事件
4. 表单事件

### Vue3
构建用户界面的渐进式js框架（能快速构建项目）
如何使用，看官方文档 https://cn.vuejs.org/
准备：
1. 导入vue模块
2. 创建vue应用实例
3. 准备元素（div）
准备数据
用插值表达式（{{message}}）来渲染页面
		插值表达式：
		类似于模板引擎中的“输出表达式”，主要用于渲染指定的数据
		插值表达式不能出现在标签内部
		
![[Pasted image 20251017193704.png]]
==createApp 是用来创建一个Vue，这个Vue有怎样的功能呢，这取决于你在createApp里定义的函数，那这一套功能用在哪个盒子上呢？取决于mount里的值（vue应用实例接管名为app的div标签）==

vue常见指令：
（这些指令是特殊属性）
![[Pasted image 20251018102843.png]]

v-for指令
![[Pasted image 20251018103233.png]]
（在js当中，方括号括起来的是数组，花括号括起来的是对象）

v-bind：动态为标签中的属性绑定一个值，解决了插值表达式不能在标签内部使用的问题。
![[Pasted image 20251018104431.png]]

v-if& v-show
![[Pasted image 20251018104847.png]]

v-model
![[Pasted image 20251018105815.png]]

v-on
![[Pasted image 20251018110608.png]]

#### Ajax（看不懂，暂时跳过）

什么是AJAX：异步的html和xml
作用：通过ajax可以给服务器发送请求，并获取服务器发送过来的数据
异步交互：在==不重新加载整个页面==的情况下与==服务器交换数据==并==更新部分页面==的技术

工具：Axios
使用步骤：
![[Pasted image 20251018115219.png]]
.then 后面跟的是成功回调函数，.catch后面跟的是失败回调函数





## 后端

### web基础

#### MAVEN
管理和构建后端java项目的工具
maven的用处
1. 方便的jar包依赖管理
2. 标准化的项目管理（快速编译打包发布）
3. 同一的项目结构

maven的生命周期
![[Pasted image 20251019161345.png]]
1. clean： 删除已有target
2. compile：生成target
3. test：
4. package： 在target下生成一个jar包
5. install：执行compile，test，package操作，并将当前项目安装到本地仓库

##### 测试（暂时跳过）
单元测试（白），集成测试（灰），系统测试（黑），验收测试（黑）
白盒测试，黑盒测试，灰盒测试

JUnit单元测试：
![[Pasted image 20251019170556.png]]
 断言：
 ![[Pasted image 20251019172230.png]]
 
#### springboot web入门

#### http

#### springboot web 案例

#### 分层解耦



## 部署
