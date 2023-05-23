# 1

•
TCP 和 UDP 的区别
参考回答：
（1）TCP 是面向连接的，udp 是无连接的即发送数据前不需要先建立链接。
（2）TCP 提供可靠的服务。也就是说，通过 TCP 连接传送的数据，无差错，不丢失，
不重复，且按序到达;UDP 尽最大努力交付，即不保证可靠交付。 并且因为 tcp 可靠，
面向连接，不会丢失数据因此适合大数据量的交换。
（3）TCP 是面向字节流，UDP 面向报文，并且网络出现拥塞不会使得发送速率降低
（因此会出现丢包，对实时的应用比如 IP 电话和视频会议等）。
（4）TCP 只能是 1 对 1 的，UDP 支持 1 对 1,1 对多。
（5）TCP 的首部较大为 20 字节，而 UDP 只有 8 字节。
（6）TCP 是面向连接的可靠性传输，而 UDP 是不可靠的。

# 2

•
一个图片 url 访问后直接下载怎样实现？
参考回答：
请求的返回头里面，用于浏览器解析的重要参数就是 OSS 的 API 文档里面的返回 http
头，决定用户下载行为的参数。
下载的情况下：
1. x-oss-object-type:
Normal
2. x-oss-request-id:
598D5ED34F29D01FE2925F41
3. x-oss-storage-class:
Standard

# 3

•
说一下 web Quality（无障碍）
参考回答：
能够被残障人士使用的网站才能称得上一个易用的（易访问的）网站。
残障人士指的是那些带有残疾或者身体不健康的用户。
使用 alt 属性：
<img src="person.jpg" alt="this is a person"/>
有时候浏览器会无法显示图像。具体的原因有：
用户关闭了图像显示
浏览器是不支持图形显示的迷你浏览器
浏览器是语音浏览器（供盲人和弱视人群使用）
如果您使用了 alt 属性，那么浏览器至少可以显示或读出有关图像的描述。

# 4

•
说一下 HTML5 drag api
参考回答：
dragstart：事件主体是被拖放元素，在开始拖放被拖放元素时触发，。
darg：事件主体是被拖放元素，在正在拖放被拖放元素时触发。
dragenter：事件主体是目标元素，在被拖放元素进入某元素时触发。
dragover：事件主体是目标元素，在被拖放在某元素内移动时触发。
dragleave：事件主体是目标元素，在被拖放元素移出目标元素是触发。
drop：事件主体是目标元素，在目标元素完全接受被拖放元素时触发。
dragend：事件主体是被拖放元素，在整个拖放操作结束时触发
# 5

•
说一下 http2.0
参考回答：
首先补充一下，http 和 https 的区别，相比于 http,https 是基于 ssl 加密的 http 协
议
简要概括：http2.0 是基于 1999 年发布的 http1.0 之后的首次更新。
提升访问速度（可以对于，请求资源所需时间更少，访问速度更快，相比 http1.0）
允许多路复用：多路复用允许同时通过单一的 HTTP/2 连接发送多重请求-响应信息。
改善了：在 http1.1 中，浏览器客户端在同一时间，针对同一域名下的请求有一定数
量限制（连接数量），超过限制会被阻塞。
二进制分帧：HTTP2.0 会将所有的传输信息分割为更小的信息或者帧，并对他们进行二
进制编码
首部压缩
服务器端推送

# 6

fetch 发送 2 次请求的原因
参考回答：
fetch 发送 post 请求的时候，总是发送 2 次，第一次状态码是 204，第二次才成功？
原因很简单，因为你用 fetch 的 post 请求的时候，导致 fetch 第一次发送了一个
Options 请求，询问服务器是否支持修改的请求头，如果服务器支持，则在第二次中发
送真正的请求。

# 7

•
说一下 web worker

参考回答：
在 HTML 页面中，如果在执行脚本时，页面的状态是不可相应的，直到脚本执行完成
后，页面才变成可相应。web worker 是运行在后台的 js，独立于其他脚本，不会影响
页面你的性能。并且通过 postMessage 将结果回传到主线程。这样在进行复杂操作的
时候，就不会阻塞主线程了。
如何创建 web worker：
检测浏览器对于 web worker 的支持性
创建 web worker 文件（js，回传函数等）
创建 web worker 对象

# 8

对 HTML 语义化标签的理解
参考回答：
HTML5 语义化标签是指正确的标签包含了正确的内容，结构良好，便于阅读，比如 nav
表示导航条，类似的还有 article、header、footer 等等标签。

# 9

iframe 是什么？有什么缺点？
参考回答：
定义：iframe 元素会创建包含另一个文档的内联框架
提示：可以将提示文字放在<iframe></iframe>之间，来提示某些不支持 iframe 的浏
览器
缺点：
会阻塞主页面的 onload 事件
搜索引擎无法解读这种页面，不利于 SEO
iframe 和主页面共享连接池，而浏览器对相同区域有限制所以会影响性能。

# 10

Cookie 如何防范 XSS 攻击
参考回答：
XSS（跨站脚本攻击）是指攻击者在返回的 HTML 中嵌入 javascript 脚本，为了减轻这
些攻击，需要在 HTTP 头部配上，set-cookie：
httponly-这个属性可以防止 XSS,它会禁止 javascript 脚本来访问 cookie。
secure - 这个属性告诉浏览器仅在请求为 https 的时候发送 cookie。
结果应该是这样的：Set-Cookie=<cookie-value>.....

# 11
•
cookie session 区别
参考回答：
1.
cookie 数据存放在客户的浏览器上，session 数据放在服务器上。
2.
cookie 不是很安全，别人可以分析存放在本地的 COOKIE 并进行 COOKIE 欺
骗
考虑到安全应当使用 session。
3.
session 会在一定时间内保存在服务器上。当访问增多，会比较占用你服务
器的性能
考虑到减轻服务器性能方面，应当使用 COOKIE。
4.
单个 cookie 保存的数据不能超过 4K，很多浏览器都限制一个站点最多保存
20 个 cookie。

# 12
•
讲讲 304
参考回答：
304：如果客户端发送了一个带条件的 GET 请求且该请求已被允许，而文档的内容（自
上次访问以来或者根据请求的条件）并没有改变，则服务器应当返回这个 304 状态
码。

# 13
•
GET 和 POST 的区别
参考回答：
get 参数通过 url 传递，post 放在 request body 中。
get 请求在 url 中传递的参数是有长度限制的，而 post 没有。
get 比 post 更不安全，因为参数直接暴露在 url 中，所以不能用来传递敏感信息。
get 请求只能进行 url 编码，而 post 支持多种编码方式
get 请求会浏览器主动 cache，而 post 支持多种编码方式。
get 请求参数会被完整保留在浏览历史记录里，而 post 中的参数不会被保留。
GET 和 POST 本质上就是 TCP 链接，并无差别。但是由于 HTTP 的规定和浏览器/服务器
的限制，导致他们在应用过程中体现出一些不同。
GET 产生一个 TCP 数据包；POST 产生两个 TCP 数据包。

# 14
•
HTTP 支持的方法
参考回答：
GET, POST, HEAD, OPTIONS, PUT, DELETE, TRACE, CONNECT

# 15
•
说一下浏览器缓存
参考回答：
缓存分为两种：强缓存和协商缓存，根据响应的 header 内容来决定。
强缓存相关字段有 expires，cache-control。如果 cache-control 与 expires 同时存
在的话，cache-control 的优先级高于 expires。
协商缓存相关字段有 Last-Modified/If-Modified-Since，Etag/If-None-Match

# 16
•
HTML5 新增的元素
参考回答：
首先 html5 为了更好的实践 web 语义化，增加了 header，footer，nav,aside,section
等语义化标签，在表单方面，为了增强表单，为 input 增加了 color，
emial,data ,range 等类型，在存储方面，提供了 sessionStorage，localStorage,和
离线存储，通过这些存储方式方便数据在客户端的存储和获取，在多媒体方面规定了
音频和视频元素 audio 和 vedio，另外还有地理定位，canvas 画布，拖放，多线程编
程的 web worker 和 websocket 协议。

# 17
•
常见的 HTTP 的头部
参考回答：
可以将 http 首部分为通用首部，请求首部，响应首部，实体首部
通用首部表示一些通用信息，比如 date 表示报文创建时间，
请求首部就是请求报文中独有的，如 cookie，和缓存相关的如 if-Modified-Since
响应首部就是响应报文中独有的，如 set-cookie，和重定向相关的 location，
实体首部用来描述实体部分，如 allow 用来描述可执行的请求方法，content-type 描
述主题类型，content-Encoding 描述主体的编码方式。

# 18
cache-control 的值有哪些
参考回答：
cache-control 是一个通用消息头字段被用于 HTTP 请求和响应中，通过指定指令来实
现缓存机制，这个缓存指令是单向的，常见的取值有 private、no-cache、max-age、
must-revalidate 等，默认为 private。

# 19
浏览器在生成页面的时候，会生成那两颗树？
参考回答：
构造两棵树，DOM 树和 CSSOM 规则树，
当浏览器接收到服务器相应来的 HTML 文档后，会遍历文档节点，生成 DOM 树，
CSSOM 规则树由浏览器解析 CSS 文件生成。

# 20
•
输入 URL 到页面加载显示完成发生了什么?
参考回答：
DNS 解析
TCP 连接
发送 HTTP 请求
服务器处理请求并返回 HTTP 报文
浏览器解析渲染页面
连接结束

# 21
•
说一下对 Cookie 和 Session 的认知，Cookie 有哪些限制？
参考回答：
1.
cookie 数据存放在客户的浏览器上，session 数据放在服务器上。
2.
cookie 不是很安全，别人可以分析存放在本地的 COOKIE 并进行 COOKIE 欺
骗
考虑到安全应当使用 session。
3.
session 会在一定时间内保存在服务器上。当访问增多，会比较占用你服务
器的性能
考虑到减轻服务器性能方面，应当使用 COOKIE。
4.
单个 cookie 保存的数据不能超过 4K，很多浏览器都限制一个站点最多保存
20 个 cookie。

# 22具体有哪些请求头是跟缓存相关的
参考回答：
缓存分为两种：强缓存和协商缓存，根据响应的 header 内容来决定。
强缓存相关字段有 expires，cache-control。如果 cache-control 与 expires 同时存
在的话，cache-control 的优先级高于 expires。
协商缓存相关字段有 Last-Modified/If-Modified-Since，Etag/If-None-Match

# 23
•
cookie 有哪些编码方式？
参考回答：
encodeURI（）

# 24
•
浏览器输入网址到页面渲染全过程
参考回答：
DNS 解析
TCP 连接
发送 HTTP 请求
服务器处理请求并返回 HTTP 报文
浏览器解析渲染页面
连接结束

# 25
•
http 常见的请求方法
参考回答：
get、post，这两个用的是最多的，还有很多比如 patch、delete、put、options 等等

# 26
•
web 性能优化
参考回答：
降低请求量：合并资源，减少 HTTP 请求数，minify / gzip 压缩，webP，lazyLoad。
加快请求速度：预解析 DNS，减少域名数，并行加载，CDN 分发。
缓存：HTTP 协议缓存请求，离线缓存 manifest，离线数据缓存 localStorage。
渲染：JS/CSS 优化，加载顺序，服务端渲染，pipeline。

# 27
•
transition 和 animation 的区别
参考回答：
Animation 和 transition 大部分属性是相同的，他们都是随时间改变元素的属性值，
他们的主要区别是 transition 需要触发一个事件才能改变属性，而 animation 不需要
触发任何事件的情况下才会随时间改变属性值，并且 transition 为 2 帧，从
from .... to，而 animation 可以一帧一帧的。

# 28
•
说一下块元素和行元素
参考回答：
块元素：独占一行，并且有自动填满父元素，可以设置 margin 和 pading 以及高度和
宽度
行元素：不会独占一行，width 和 height 会失效，并且在垂直方向的 padding 和
margin 会失
效。

# 29
•
css3 新特性
参考回答：
开放题。CSS3 边框如 border-radius，box-shadow 等；CSS3 背景如 background-
size，background-origin 等；CSS3 2D，3D 转换如 transform 等；CSS3 动画如
animation 等。
参考 https://www.cnblogs.com/xkweb/p/5862612.html

# 30
•
怎么样让一个元素消失，讲讲
参考回答：
display:none; visibility:hidden; opacity: 0; 等等

# 31
•
CSS3 中对溢出的处理
参考回答：
cnkOhu
text-overflow 属性，值为 clip 是修剪文本；ellipsis 为显示省略符号来表被修剪的
文本；string 为使用给定的字符串来代表被修剪的文本。

# 32
•
float 的元素，display 是什么
参考回答：
display 为 block

# 33
•
隐藏页面中某个元素的方法
参考回答：
display:none; visibility:hidden; opacity: 0; position 移到外部，z-index 涂层
遮盖等等

# 34
•
calc 属性
参考回答：
Calc 用户动态计算长度值，任何长度值都可以使用 calc()函数计算，需要注意的是，
运算符前后都需要保留一个空格，例如：width: calc(100% - 10px)；

# 35
•
什么是 BFC
参考回答：
BFC 也就是常说的块格式化上下文，这是一个独立的渲染区域，规定了内部如何布局，
并且这个区域的子元素不会影响到外面的元素，其中比较重要的布局规则有内部 box
垂直放置，计算 BFC 的高度的时候，浮动元素也参与计算，触发 BFC 的规则有根元
素，浮动元素，position 为 absolute 或 fixed 的元素，display 为 inline-block，
table-cell，table-caption，flex，inline-flex，overflow 不为 visible 的元素

# 36
• z-index 的定位方法
参考回答：
z-index 属性设置元素的堆叠顺序，拥有更好堆叠顺序的元素会处于较低顺序元素之
前，z-index 可以为负，且 z-index 只能在定位元素上奏效，该属性设置一个定位元素
沿 z 轴的位置，如果为正数，离用户越近，为负数，离用户越远，它的属性值有
auto，默认，堆叠顺序与父元素相等，number，inherit，从父元素继承 z-index 属性
的值

# 37
•
用的最多的 css 属性是啥？
参考回答：
用的目前来说最多的是 flex 属性，灵活但是兼容性方面不强。

# 38
•
line-height 和 height 的区别
参考回答：
line-height 一般是指布局里面一段文字上下行之间的高度，是针对字体来设置的，
height 一般是指容器的整体高度。

# 39
•
设置一个元素的背景颜色，背景颜色会填充哪些区域？
参考回答：
background-color 设置的背景颜色会填充元素的 content、padding、border 区域。

# 40
•
知道属性选择器和伪类选择器的优先级吗
参考回答：
属性选择器和伪类选择器优先级相同

# 41
•
inline-block、inline 和 block 的区别；为什么 img 是 inline 还可以
设置宽高
参考回答：
Block 是块级元素，其前后都会有换行符，能设置宽度，高度，margin/padding 水平
垂直方向都有效。
Inline：设置 width 和 height 无效，margin 在竖直方向上无效，padding 在水平方向
垂直方向都有效，前后无换行符
Inline-block：能设置宽度高度，margin/padding 水平垂直方向 都有效，前后无换行
符

# 42
•
overflow 的原理
参考回答：
要讲清楚这个解决方案的原理，首先需要了解块格式化上下文，A block formatting 
context is a part of a visual CSS rendering of a Web page. It is the region 
in which the layout of block boxes occurs and in which floats interact with 
each other.翻译过来就是块格式化上下文是 CSS 可视化渲染的一部分，它是一块区
域，规定了内部块盒 的渲染方式，以及浮动相互之间的影响关系
当元素设置了 overflow 样式且值部位 visible 时，该元素就构建了一个 BFC，BFC 在
计算高度时，内部浮动元素的高度也要计算在内，也就是说技术 BFC 区域内只有一个
浮动元素，BFC 的高度也不会发生塌缩，所以达到了清除浮动的目的。

# 43
•
清除浮动的方法
参考回答：
给要清除浮动的元素添加样式 clear，\
父元素结束标签钱插入清除浮动的块级元素，给该元素添加样式 clear
添加伪元素，在父级元素的最后，添加一个伪元素，通过清除伪元素的浮动，注意该
伪元素的 display 为 block，
父元素添加样式 overflow 清除浮动，overflow 设置除 visible 以外的任何位置

# 44
 •
box
-
sizing 的语法和基本用处
参考回答：
box-sizing 规定两个并排的带边框的框，语法为 box-sizing：content-box/border-
box/inherit
content-box：宽度和高度分别应用到元素的内容框，在宽度和高度之外绘制元素的内
边距和边框
border-box：为元素设定的宽度和高度决定了元素的边框盒，
inherit：继承父元素的 box-sizing

# 45
 •
使元素消失的方法有哪些？
参考回答：
1. opacity：0，该元素隐藏起来了，但不会改变页面布局，并且，如果该元素已经绑
定一些事件，如 click 事件，那么点击该区域，也能触发点击事件的
2. visibility：hidden，该元素隐藏起来了，但不会改变页面布局，但是不会触发该
元素已经绑定的事件
3. display：none，把元素隐藏起来，并且会改变页面布局，可以理解成在页面中把
该元素删除掉。

# 46
•
说说盒子模型
参考回答：
CSS 盒模型本质上是一个盒子，封装周围的 HTML 元素，它包括：边距，边框，填充，
和实际内容。
标准盒模型：一个块的总宽度=width+margin(左右)+padding(左右)+border(左右)
怪异盒模型：一个块的总宽度=width+margin（左右）（既 width 已经包含了 padding
和 border 值）
如何设置：box-sizing:border-box

# 47
•
怎么隐藏一个元素
参考回答：
1. opacity：0，该元素隐藏起来了，但不会改变页面布局，并且，如果该元素已经绑
定一些事件，如 click 事件，那么点击该区域，也能触发点击事件的
2. visibility：hidden，该元素隐藏起来了，但不会改变页面布局，但是不会触发该
元素已经绑定的事件
3. display：none，把元素隐藏起来，并且会改变页面布局，可以理解成在页面中把
该元素删除掉。

# 48
•
display:none 和 visibilty:hidden 的区别
参考回答：
1. visibility：hidden，该元素隐藏起来了，但不会改变页面布局，但是不会触发该
元素已经绑定的事件
2. display：none，把元素隐藏起来，并且会改变页面布局，可以理解成在页面中把
该元素删除掉。

# 49
• css 的常用选择器
参考回答：
id 选择器，类选择器，伪类选择器等

# 50
• css 预处理器有什么
参考回答：
less，sass 等



