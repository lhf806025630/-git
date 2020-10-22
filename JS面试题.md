# JS面试题

### 1：你如何理解闭包

闭包就是能够读取其他函数内部变量的函数，或者子函数在外调用，子函数所在的父函数的作用域不会被释放。

### 2：事件循环（EventLoop）（异步对事件循环影响）

1：首先js会执行完所有的同步任务

2：检测微任务队列，依次执行所有微任务

3：检测宏任务队列，依次执行宏任务

  每次执行完宏任务，都会检测是否产生了新的微任务，如果有，转而执行微任务。
  (总是循环检测是否有微任务，如果有，就去执行)

### 3：ES6的新特性

let、const，
变量的解构赋值，
promise对象，
await/async，
块级作用域，
箭头函数，
class（类），
...展开运算符，
模板字符串，
import导入/export导出，...

### 4：promise和then的参数

promise: resolve,reject 

then: resolve的实参

promise构造函数是同步执行的，then方法是异步执行的

### 5：如何理解JS的异步

异步操作的代码，总是会在所有同步代码执行完毕之后才执行

异步操作的性质： 无代码阻塞

两种异步类型：宏任务，微任务（promise的then，其它都是宏任务）
先执行微任务再执行宏任务

### 6：跨域

两个不同origin（源）的文件企图共享数据
【当两个页面需要共享数据，却又违反了同源策略，都会形成跨域】

源（origin）: 协议，域名（IP），端口

同源策略: 需要共享数据的两个页面的源（origin）都必须完全一样

### 7：arguments

实参列表，用于获取函数的参数

（ES6中的rest参数（...变量名）  代替 arguments变量）

arguments是类数组对象，有length属性，不能调用数组方法

可用Array.from()转换

### 8：原型链。

对象中的__proto__（对象原型）指向构造函数的prototype（原型对象），

构造函数中的prototype（原型对象）的__proto__（对象原型）指向Object。

### 9：proxy原理

### 10：Set去重原理。

### 11：常用数组方法

push()，pop()，shift()，unshift()，splice()，sort()，reverse()，map()等

### 12：数组去重

法一：indexOf循环去重

法二：ES6 Set去重；Array.from(new Set(array))

法三：Object 键值对去重；把数组的值存成 Object 的 key 值，比如 Object[value1] = true，在判断另一个值的时候，如果 Object[value2]存在的	 	 话，就说明该值是重复的。

### 13：promise有啥缺点

### 14：cookie，localstorage，sessionStorage有啥区别

生命周期
cookie：可以通过expires设置失效时间，不设置默认关闭浏览器即失效
localStorage：除非手动清除，否则永久保存
sessionStorage：仅在当前会话时候生效，关闭页面即失效

存储大小
cookie:4KB左右
localStorage、sessionStorage:可以保存5M的信息

HTTP请求
cookie:每次都会携带在http头中，过多使用cookie会带来性能问题
localStorage、sessionStorage:仅在客户端（即浏览器）中保存，不参与和服务器的通信

易用性
cookie:需要程序员自己封装，源生的Cookie接口不友好
localStorage、sessionStorage：源生接口可以接受，亦可再次封装来对Object和Array有更好的支持

应用场景
cookie：适合识别用户登录
localStorage和sessionStorage唯一的差别一个是永久保存在浏览器里面，一个是关闭网页就清除了信息
localStorage：可以用来跨页面传递参数
sessionStorage：用来保存临时数据，防止用户刷新页面之后丢失参数

### 15：let，const，var的区别。

1、var能重复声明，let、const不能

2、var能发送变量提升，let、const不能

3、var无块级作用域，let、const有

4、var声明的全局变量会变成window的属性，let、const不会

5、const声明的同时必须赋值，声明之后就不能改变

### 16：箭头函数的理解

1、箭头函数没有this，所以需要通过查找作用域链来确定this的值，这就意味着如果箭头函数被非箭头函数包含，this绑定的就是最近一层非箭头函数的this

2、箭头函数没有自己的arguments对象，但是可以访问外围函数的arguments对象

3、不能通过new关键字调用，同样也没有new.target值和原型

### 17：怎么用原生js解决滚动条的出线

### 18：函数声明和函数表达式的区别，它们在变量提升的时候有什么不一样

### 19：变量提升和预解析的理解

### 20：setTimeout的时间是不是精准的，如何实现精准定时；

不精确

精准定时：使用时间戳来实现，

### 21：html5新特性有哪些

1.语义化标签
2.本地存储
3.

### 22：DOM事件的3个阶段

1、事件捕获阶段

2、处于目标阶段

3、事件冒泡阶段

### 23：防抖截流解决的问题和实现

防抖节流：防止事件频繁触发（为了性能）

原理：
在单位时间内不触发、少触发，单位时间后可再次触发
解决方法：通过定时器、时间戳来设置一个时间间隔、标志位

### 24：深浅拷贝的区别

### 25：new一个Object发生了什么（New做了什么）

new 操作符新建了一个空对象，这个对象原型指向构造函数的prototype，执行构造函数后返回这个对象。

### 26：事件委托原理

给父元素添加事件，处理子元素的事件逻辑

原理：通过事件冒泡来实现

### 27：如何解决跨域（不要再说jsonp了）

cors和代理（proxy）

CORS：服务端设置Access-Control-Allow-Origin即可，前端无须设置，若要带cookie请求，前后端都需要设置。
代理跨域：启一个代理服务器，实现数据的转发

### 28：ajax的原理。

实际就是在问ajax的原生写法。然后凸出这是一个异步的监听等待过程就可以了。

### 29：axios的原理。（promise原理）

实际是在问promise

### 30：promise解决了啥问题，3个状态是啥。

promise是一种异步编程解决方案。解决了回调地狱的问题，解决了信任问题。

3个状态分别是pendding，resolve，reject。

### 31：get和post的区别

GET把参数包含在URL中，POST通过request的body传递参数.（request 是一个原生的请求类。还有响应类）

GET 有长度限制，2000字节左右，因为受到url长度限制。POST没有长度限制。

GET请求只能进行url编码，而POST支持多种编码方式。

GET请求参数会被完整保留在浏览器历史记录里，而POST中的参数不会被保留。

GET在浏览器回退时是无害的，而POST会再次提交请求。

GET产生的URL地址可以被Bookmark，而POST不可以。