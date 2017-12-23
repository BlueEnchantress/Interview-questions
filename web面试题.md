

###1. 行内元素有哪些?块级元素有哪些?`CSS`的盒模型?

- **内联元素:**

  - `a `- 锚点
    - `abbr` - 缩写
    - `acronym` - 首字
    - `b` - 粗体(不推荐)
    - `bdo - bidi override`
    - `big` - 大字体
    - `br` - 换行
    - `cite` - 引用
    - `code` - 计算机代码(在引用源码的时候需要)
    - `dfn` - 定义字段
    - `em` - 强调
    - `font` - 字体设定(不推荐)
    - `i` - 斜体
    - `img` - 图片
    - `input` - 输入框
    - `kbd` - 定义键盘文本
    - `label `- 表格标签
    - `q `- 短引用
    - `s` - 中划线(不推荐)
    - `samp` - 定义范例计算机代码
    - `select` - 项目选择
    - `small` - 小字体文本
    - `span `- 常用内联容器，定义文本内区块
    - `strike` - 中划线
    - `strong` - 粗体强调
    - `sub` - 下标
    - `sup` - 上标
    - `textarea` - 多行文本输入框
    - `tt` - 电传文本
    - `u `- 下划线
    - `var` - 定义变量

- **块级元素:**

  * `address` - 地址
    * `blockquote `- 块引用
    * `center` - 举中对齐块
    * `dir` - 目录列表
    * `div` - 常用块级容易，也是`css layout`的主要标签
    * `dl `- 定义列表
    * `fieldset - form`控制组
    * `form `- 交互表单
    * `h1`- 大标题
    * `h2 `- 副标题
    * `h3 `- 3级标题
    * `h4 `- 4级标题
    * `h5 `- 5级标题
    * `h6 `- 6级标题
    * `hr `- 水平分隔线
    * `isindex - input prompt`
    * `menu `- 菜单列表
    * `noframes - frames`可选内容，（对于不支持frame的浏览器显示此区块内容
    * `noscript` - 可选脚本内容（对于不支持script的浏览器显示此内容）
    * `ol` - 排序表单
    * `p` - 段落
    * `pre` - 格式化文本
    * `table` - 表格
    * `ul` - 非排序列表

- **`CSS`盒模型:**

  * ```
    内容  +  padding  +  border  +  margin     从内向外
    ```

    ​

### 2. display 有多少个属性

- **有19个属性**
  * `none` 元素为隐藏状态
  * `block`块级元素,前后会带有换行符,且元素为显示状态
  * `inline` 默认属性.元素会被显示为内联(**行内**)元素,元素前后没有换行符
  * `inline-block`行内快元素.(2.1新增的值)
  * `run-in`元素会根据上下文作为块级元素或者内联元素显示
  * `compact`从2.1中删除
  * `marker` 从2.1中删除
  * `table`元素会作为块级表格显示(**类似`<table>`**),表格前后带有换行符
  * `inline-table`元素会作为内联表格显示(**类似`<table>`**),表格前后没有换行符
  * `table-row-group`元素会作为一个或多个行的分组来显示(**类似`<tbody>`**)
  * `table-header-group`元素会作为一个或多个行的分组来显示(**类似`<thead>`**)
  * `table-footer-group`元素会作为一个或多个行的分组来显示(**类似`<tfood>`**)
  * `table-row`元素会作为一个或多个行的分组来显示(**类似`<tr>`**)
  * `table-column-group`元素会作为一个或多个行的分组来显示(**类似`<colgroup>`**)
  * `table-column`元素会作为一个单元格列显示(**类似`<col>`**)
  * `table-cell`元素会作为一个表单单元格显示(**类似`<td>和<th>`**)
  * `table-caption`元素会作为一个表格标题显示(**类似`<caption>`**)
  * `inherit`规定应该从父元素继承`display`属性的值

###3.清除浮动的几种方式.各自的优缺点?

* **8种方式**

  - **1、父级`div`定义`height`**

    - 原理:  父级`div` 手动定义`height`,就解决了父级`div`无法自动获取到高度的问题
    - 优点:  简单,代码少,容易掌握
    - 缺点:  只适合高度固定的布局,要给出精确的高度,如果高度和父级`div`不一样时,会产生问题
    - 不推荐使用

  - **2、结尾处加空`div`标签`clear:both`**

    - 原理:  添加一个空`div` ,利用`css`提高的`clear:both`清除浮动,让父级`div` 能自动获取到高度
    - 优点:  简单,代码少,浏览器支持好,不容易出现怪问题
    - 缺点:  不少初学者不理解原理;如果页面浮动布局多,就要增加很多空`div`,让人感觉很不爽
    - 不推荐使用,但此方法是以前主要使用的一种清除浮动方法

  - **3、父级`div`定义伪类:`after和zoom`**

    - 原理:  `IE8`以上和非`IE`浏览器才支持:`after`,原理和方法2优点类似,`zoom`可解决`ie6,ie7`浮动问题
    - 优点:  浏览器支持好,不容易出现怪问题(目前:大型网站都有使用,如:腾讯、网易、新浪等)
    - 缺点:  代码多,不少初学者不理解原理;要两句代码结合使用,才能让主流浏览器都支持
    - 推荐使用,建议定义公共类,以减少`CSS`代码

  - **4、父级`div`定义`overflow:hidden`**

    - 原理:  必须定义`width`或`zoom`:1,同时不能定义`height`,使用`overflow:hidden`时,浏览器会自动检查浮动区域的高度
    - 优点:  简单,代码少,浏览器支持好
    - 缺点:  不能和`position`配合使用,因为超出的尺寸的部分会被隐藏
    - 只推荐没有使用`position`或对`overflow:hidden`理解比较深的人使用

  - **5、父级`div`定义`overflow:auto`**

    - 原理:  必须定义`width`或`zoom`:1,同时不能定义`height`,使用`overflow:auto`时,浏览器会自动检查浮动区域的高度
    - 优点:  简单,代码少,浏览器支持好
    - 缺点:  内部宽度超过父级div时,会出现滚动条
    - 不推荐使用,如果需要出现滚动条或者确保你的代码不会出现滚动条就使用

  - **6、父级`div`也一起浮动**

    - 原理:  添加一个空`div` ,利用`css`提高的`clear:both`清除浮动,让父级`div` 能自动获取到高度
    - 优点:  简单,代码少,浏览器支持好,不容易出现怪问题
    - 缺点:  不少初学者不理解原理;如果页面浮动布局多,就要增加很多空`div`,让人感觉很不爽
    - 不推荐使用,但此方法是以前主要使用的一种清除浮动方法

  - **7、父级`div`定义`dispaly:table`**

    - 原理:  添加一个空`div` ,利用`css`提高的`clear:both`清除浮动,让父级`div` 能自动获取到高度
    - 优点:  简单,代码少,浏览器支持好,不容易出现怪问题
    - 缺点:  不少初学者不理解原理;如果页面浮动布局多,就要增加很多空`div`,让人感觉很不爽
    - 不推荐使用,但此方法是以前主要使用的一种清除浮动方法

  - **8、结尾处加`br`标签`clear:both`**
    - 原理: 父级`div`定义`zoom:1`来解决`IE`浮动问题，结尾处加`br`标签`clear:both`
    - 优点:  简单,代码少,浏览器支持好,不容易出现怪问题
    - 不推荐使用

### 4.  `CSS3` 都有那些新内容?

* **1.颜色**

  * `RGBA`,`HSLA`模式

* **2.文字阴影**

  * `text-shadow`

* **3.边框**

  * 圆角`border-radius`  边框阴影`box-shadow`

* **4.盒子模型**

  - `box-sizing`

* **5.背景**

  * `background-size`设置背景图片的尺寸
  * `background-origin`设置背景图片的原点
  * `background-clip`设置背景图片的裁切区域,以`,`分隔可以设置多背景,用于自适应布局

* **6.渐变**

  * `linear-gradient、radial-gradient`

* **7.过渡**

  - `transition`,可实现动画
  - `@keyframes`用于创建封装动画函数
  - `animation`动画函数

* **8.自定义动画**

* **9.在`CSS`中唯一引入的伪元素是`::selection`**

* **10.媒体查询,多栏布局**

* **11.border-image**

* **12.`2D`转换**

  * `transform:translate(x,y)rotate(x,y)skew(x,y)scale(x,y)`

* **13.`3D`转换**

  ​

### 5.  `CSS Sprite`是什么,谈谈这个技术的优缺点

* `CSS Sprite`是一种网页图片应用处理方式,就是把网页重一些背景图片整合到一张图片文件中,再利用	`CSS`的`background-image`,`background-repeat`,`background-position`的组合进行背景定位。
* 优点:
  * 减少网页的`http`请求,提高性能,这也是`CSS Sprites`最大的优点,也是其被广泛传播和应用的主要原因
  * 减少图片的字节:多张图片合并成一张图片的字节小于多张图片的字节总和
  * 减少了命名困扰:只需对一张集合的图片命名,不需要对每一个小元素进行命名提高制作效率
  * 更换风格方便:只需要在一张或少张图片上修改图片的颜色或样式,整个网页的风格就可以改变,维护起来更加方便
* 缺点:
  * 图片合成比较麻烦
  * 背景设置时,需要得到每一个背景单元的精确位置
  * 维护合成图片时,最好只是往下加图片,而不要更改已有图片

### 6.  你做的页面在哪些浏览器测试过?这些浏览器内核分别是什么

* 测试浏览器
  * `IE`
    * 内核: `Trident`
  * 谷歌`Chrome`
    * 内核: `Chromium`
  * 苹果`Safari`
    * 内核:  `WebKit`
  * 火狐`Firefox`
    * 内核:  `Gecko`
  * 欧朋`Opera`
    * 内核:  `Presto`

### 7.  `javascript`的`typeof`返回哪些数据类型

* **1.返回数据类型**
  * undefined
  * string
  * boolean
  * number
  * symbol(`ES6`)
  * Object
  * Function
* **2.强制类型转换**
  * `Number`(参数)把任何类型转换成数值类型
  * `parseInt`(参数1,参数2)将字符串转换成整数
  * `parseFloat`()将字符串转换成浮点数字
  * `string`(参数)可以将任何类型转换成字符串
  * `Boolean`()可以将任何类型的值转换成布尔值
* **3.隐士类型转换**
  * 四则运算
    * 加法运算符+是双目运算符,只要其中一个是string类型,表达式的值便是一个`String`
    * 对于其他的四则运算,只有其中一个是`Number`类型,表达式的便是一个`Number`
    * 对于非法字符的情况通常会返回`NaN:'1'*'a'  //  =>NaN`这是因为`parseInt(a)`值为`NaN`,`1*NaN还是NaN`
  * 判断语句
  * Native代码调用

### 8.  `split() join()`的区别

* join函数获取一批字符串,然后用分隔符字符串将它们连接起来,从而返回一**个 **字符串

* split()函数获取一个字符串,然后在分隔符处将其断开,从而返回一 **批 **字符串

* join可以使用任何分割字符串将多个字符串连接起来,而split只能使用一个字符分隔符

* split是把一串字符串根据某个分隔符分成诺干个元素存放在一个数组里

* join是把数组中的字符串连接成一个长串,可以认为是split的逆操作

  ​

### 9.  如果有两个数组,请写出代码,将两个数组中相同的元素组成一个新数组。数组a:[1,2,3,5,8,7,6,9,4],数组b:[2,5,4,8,7,6,9,3]

```
    var c=[];
    for(var i=0;i<a.length;i++){
        for(var j=0;j<b.length;j++){
          if(a[i]===b[j]){
            c.push(a[i]);
          }
        }
    }
    console.log(c);
```



### 10.  请谈谈对 `webapp` 的理解

* ​


### 11.  `Javascript` 的数据类型有哪些?如何准确检测数据类型?

* 数据类型:

  * `Object`对象类型

  * `Number`数字类型

  * `String`字符串类型

  * `Boolean`布尔类型:`true`或者为`false`

  * `Null`

  * `Underfined`

    ​

* 检测方法:

  * `Typeof`:`typeof null 返回  object`

    如果`typeof`一个量,是基本类型`(如:100,hello)`等的话,`typeof`会尝试得到最基本的类型,如果是函数名`(Object,Number,String)`,则返回`function`,`typeof null`,返回结果`object`,这是一个很早之前的BUG,一直至今

    ​

  * `instanceof`:`[1,2]instanceof Array  返回  true`

    `instanceof`会沿用着原型链查找,如果左边对象的原型链上,具有右边的对象,name会返回true,并且注意只用于判断扩展的对象类型`(非number,string等)`

###12.  请从编码和项目实施两个角度谈谈对`JS`的优化[口述]  

* 注意作用域:尽量少的存在全局变量,表面With语句
* 选择正确的方法
* 避免不必要的属性查找
* 优化循环
* 展开循环
* 避免双重解释
* 性能的其它注意事项
* 避免多个变量声明
* 避免双重解释`(JS代码解析JS代码)`
* 避免插入迭代值
* 只要可以就使用原生方法写
* 最小化语句数量
* 使用数组和对象字面量,避免使用构造函数`Array(),Object()`
* 优化DOM交互最小化现场更新,多使用`innerHTML`



### 13.  请谈谈如何对`CSS`性能方面做优化[口述]

* **加载性能**

  * 不用import,压缩等等,主要是减少文件体积,减少阻塞加载,提高并发方面

* **选择器性能**

  * selector的对整体性能的影响可以忽略不计

* **渲染性能**

  * 优化最重要的点:页面渲染减少`junky`,`text-shadow`,关闭字体抗锯齿,优化动画实现方法,合理利用`GPU`加速等

* **可维护性,健壮性**

  * 合理命名,结构层次设计足够健壮,对样式进行抽象复用

* `CSS Lint`一个发现书写问题,提升性能的工具,具体可以看这个文章:    挪墨的空间/关注 `CSS Lint`

  * 修复解析错误,表面使用多类选择符

  * 移除空的`css`规则

  * 正确使用display的属性

    * ```
      display:inline后不应该再使用width,height,margin,padding以及float
      ```

    * ``` 
      display:inline-block后不应该再使用float
      ```

    * ```
      display:block后不应该再使用vertival-align
      ```

    * ```
      display:table-*后不应该再使用margin,float
      ```

      ​

### 14.  页面图片加载太多,一般如何处理?请写出你的代码?如何延迟和预先加载?

* 压缩图片

* `echo.js`插件:轻量级懒加载

* 懒加载:现加载用户需要的图片,剩下的当用户将要看到的时候,再去加载

  * ```
    将页面里所有img属性src属性用data-xx代替，当页面滚动直至此图片出现在可视区域时，用js取到该图片的data-xx的值赋给src
    ```



* 分帧Frame加载:页面很长,只加载前面显示的一部分,当用户下拉的时候再加载下面的塞进去
* 使用`BigPipe`技术
* `JS`进行异步加载
* 思路:
  * 对于用户关注的重要内容优先加载,用户不关注的懒加载,减少`http`请求,合并`js,css,image`文件,压缩文件大小,异步,优化`JS`代码,浏览器`UI`线程是单线程,浏览器页面的渲染和`JS`执行时互相阻塞的


* 预加载:https://www.cnblogs.com/haoyijing/p/5818236.html

### 15.  页面中宽高都有哪些?

* ```
  网页可见区域宽： document.body.clientWidth;
  网页可见区域高： document.body.clientHeight;
  网页可见区域宽： document.body.offsetWidth (包括边线的宽);
  网页可见区域高： document.body.offsetHeight (包括边线的宽);
  网页正文全文宽： document.body.scrollWidth;
  网页正文全文高： document.body.scrollHeight;
  网页被卷去的高： document.body.scrollTop;
  网页被卷去的左： document.body.scrollLeft;
  网页正文部分上： window.screenTop;
  网页正文部分左： window.screenLeft;
  屏幕分辨率的高： window.screen.height;
  屏幕分辨率的宽： window.screen.width;
  屏幕可用工作区高度： window.screen.availHeight;
  ```

### 16.  什么是`Html`语义化

* 主要的标签内涵意义:如标题`H1~H2`,列表`li`,强调`strong em`等等,根据内容的结构(内容语义化),选择合适的标签(代码语义化)便于开发者阅读和写出更优雅的代码的同时让浏览器的爬虫和极其很好的解析
* **为什么要语义化**:
  * 在没有`CSS`的请款下,页面也能呈现出很好的内结构,代码结构
  * 用户体验:例如title,alt用于解释名词或者解释图片信息,label标签的活用
  * 有利于`SEO`:和搜索引擎建立良好沟通,有助于爬虫抓取更多的有效性系(爬虫依赖于标签来确定上下文和各个关键字的权重)
  * 方便其他设备解析(如屏幕阅读器,盲人阅读器,移动设备)以意义的方式来渲染网页
  * 便于团队开发和维护
* 写HTML代码时候应该注意什么:
  * 尽可能少的使用物寓意的标签div和span
  * 在语意不明显示,既可以使用div或者p时,尽量用p,因为p在默认情况下有上下间距,对兼容特殊终端有利
  * 不要使用纯样式标签,如b,font,u等,改用`css`设置
  * 需要强调的文本 ,可以包含在strong或者em标签中(浏览器预设样式,能用`CSS`指定就不用他们),strong默认样式是加粗(不要用b),em是斜体(不用i)
  * 使用表格式,标题要用caption,表头要用`thead`,主体部分用`tbody`包围,尾部用`tfoot`包围。表头和一般单元格要区分开,表头用`th`,单元格用`td`
  * 表单域要用`fieldset`标签包起来,并用`legend`标签说明表单的用途
  * 每个input标签对应的说明文本都需要使用label标签,并且通过为input设置id属性,在`lable`标签中设置`for=someld`来让个说明文本和相对应的input关联起来
* `H5`新增的语义化标签--节元素标签:http://www.html5jscss.com/html5-semantics-section.html
  * ![右击图像复制或保存图像](data:image/jpeg;base64,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)





### 17.行内块元素有哪些?  

* `img`,`input`与行内块元素性质相似,可以用`css`设置`display=inline-block`

### 18.  清除浮动的方法(代码)?

* ```
  给最后一个浮动元素后边添加独立标签,使用clear:both
  ```

* ```
  给浮动元素的父元素使用overflow:hidden
  ```

* ```
  给浮动元素的父元素设置高度
  ```

* ```
  给浮动元素的父元素使用单伪元素清除浮动:
  .clearfix.clearfix:after {
  content:”.”;
  display: block;
  height: 0;
  line-height: 0;
  visibility:hidden;
  Clear: both;
  }
  .clearfix {
  Zoom:1;
  }
  ```

* ```
  双伪元素清除浮动:
  .clearfix:before,.clearfix:after{
    content:"";
    display:table;
  }
  .clearfix:after{
    clear:both
  }
  .clearfix:after{
    zoom:1;
  }
  ```



### 19.定位方式有几种?分别是相对什么元素定位?

- **静态定位:    position:static**

  - 标准流,默认值

- **绝对定位(看脸型):    position:absolute**

  - 不占据原来的位置
  - 嵌套的盒子,父元素没有使用绝对的定位,子元素使用了绝对定位,子元素的位置基于浏览器偏移
  - 嵌套的盒子,父元素使用了绝对定位,子元素使用了绝对定位,子元素的位置基于父元素位置偏移
  - 给行内元素使用绝对定位,会转换为行内块显示模式(不推荐使用)

- **相对定位(自私型):    position:relative**

  * 相对定位不脱离标准流,还占据原来的位置
  * 相对定位永远基于自身位置偏移
  * **子绝父相**   子元素使用绝对定位,父元素使用相对定位,子元素的位置基于父元素偏移
  * 给行内元素使用相对定位,不能转换为行内块显示模式

- **固定定位:     position:fixed**

  * 固定定位定位元素脱离了标准流,不占据原来的位置
  * 固定定位的元素位置基于浏览器窗口偏移,和绝对定位的基于浏览器偏移有区别,区别是固定定位的元素不会随着滚动条滚动,绝对定个位的元素会随着滚动条滚动
  * 使用固定定位的行内元素,转换为了行内快显示模式(不推荐)

  ​

  ​

### 20.  逻辑题

* 如何能够得知一架波音飞机的重量?

  * 曹冲称象,分零件称重

    ​

### 21.  `js`常用的迭代方法列举两个,并写个方法

* ```
  1、every(): 对数组中的每一项运行给定的函数，如果该函数对每一项都返回true，则结果返回true。
  2、filter(): 对数组中的每一项运行给定函数，返回该函数会返回true的项组成的数组。
  3、forEach(): 对数组中的每一项运行给定函数，这个方法没有返回值。
  4、map(): 对数组中的每一项运行给定函数，返回每次函数调用的结果组成的数组。
  5、some(): 对数组中的每一项运行给定函数，如果该函数任意一项返回true，则返回true。
  ```

  * 以上方法不会修改数组中包含的值,最相似的是every()和some(),他们都用于查询数组中的项是否满足某个条件

  * every:传入的函数必须对数组中的每一项都返回true,这个方法才返回true

  * some:只要传入的函数对数组中的任何一项返回true,就返回true

    * ```
      var numbers = [1, 2, 3, 4, 5, 4, 3, 2, 1];

      var everyResult = numbers.every(function(item, index, array) {
          return (item > 2);
      });

      var someResult = numbers.some(function(item) {
          return (item > 2);
      });

      console.log(everyResult);      //false
      console.log(someResult);        //true
      ```

  ​	

  * filter:利用指定的函数确定是否在返回的数组中包含某一项

    * ```
      var numbers = [1, 2, 3, 4, 5, 4, 3, 2, 1];
      var filterResult = numbers.filter(function(item) {
          return (item > 2);
      });

      console.log(filterResult);  \\[3, 4, 5, 4, 3]
      ```

  * map:返回一个数组,数组的每一项都是在原始数组中的对应项上运行传入函数的结果

    * ```
      var numbers = [1, 2, 3, 4, 5, 4, 3, 2, 1];
      var mapResult = numbers.map(function(item) {
          return (item * 2);
      });

      console.log(mapResult);     //[2, 4, 6, 8, 10, 8, 6, 4, 2]
      ```

  * `forEach`:对数组中的每一项运行传入的函数,没有返回值,本质上与for循环迭代数组一样

    * ```
      var numbers = [1, 2, 3, 4, 5, 4, 3, 2, 1];
      numbers.forEach(function(item, index, arr) {
          //这里执行一些操作
      });
      ```

###22.   对常见数组结构(队列、栈等)在`javascript`的实现了解多少?在下方写出一个数组去重算法    

* **数组堆栈**

  ```
  数组堆栈：  
  public class Stack {  
      private long[] stackArray;  
      private int top;  
      private int maxSize;  
        
      public Stack(int maxSize){  
          this.maxSize = maxSize;  
          top = -1;  
          stackArray = new long[maxSize];  
      }  
      public void push(long value){  
          stackArray[++top] = value;  
          //maxSize++;  
      }  
      public long pop(){  
          return stackArray[top--];  
      }  
      public boolean isEmpty(){  
          return top == -1;  
      }  
      public boolean isFull(){  
          return maxSize == (top+1);  
      }  
      public long getTopValue(){  
          return stackArray[top];  
      }  
  }  
  测试类：  
  <pre name="code" class="java">class stackApp{  
      public static void main(String args[]){  
          Stack stack = new Stack(10);  
          stack.push(1);  
          stack.push(2);  
          stack.push(3);  
          stack.push(4);  
            
          while(!stack.isEmpty()){  
              long value = stack.pop();  
              System.out.println(" "+value);  
          }//while  
            
      }   
  }  
  ```

* **数组队列**

  ```
  class queue{
      private long[] array;
      private int front;
      private int rear;
      private int nElements;
      private int maxSize;
      
      public queue(int s){
          maxSize = s;
          array = new long[maxSize];
          front = 0;
          rear = -1;
          nElements = 0;
      }
      public void insert(long value){
          if(rear == maxSize-1){
              rear = -1;
          }
          array[++rear] = value;
          nElements++;
      }
      public long remove(){
          if(front+1 == maxSize){
              front = 0;
          }
          nElements--;
          return array[front++];
      }
      public long getFrontElement(){
          return array[front];
      }
      public boolean isEmpty(){
          return (nElements == 0);
      }
      public boolean isFull(){
          return (maxSize == nElements);
      }
      public int getNElements(){
          return nElements;
      }
  }
  测试类：
  class queueApp{
      public static void main(String args[]){
          queue que = new queue(10);
          que.insert(10);
          que.insert(20);
          que.insert(30);
          que.insert(40);
          que.insert(50);
          
          while(!que.isEmpty()){
              long temp = que.remove();
              System.out.println(" "+temp);
          }
      }
  }

  ```

* **去重算法 :**

  * 1.遍历数组:

    * 思路:新建一个数组a,遍历传入的数组b,若元素不在新数组a中就添加到新数组a中

    * 注意:判断值是否在数组的方法`indexOf`是`ECMAScript5`方法,`IE8`以下不支持

    * ```
      //判断浏览器是否支持indexOf方法
           if(!Array.prototype.indexOf){
           
           
               //新增indexOf方法
               Array.prototype.indexOf = function(item){
                   var result = -1,
                       arr_item = null;
                   if(this.length == 0) {
                       return result;
                   }
                   for(var i=0,len=this.length; i<len; i++){
                       arr_item = this[i];
                       if(arr_item === item){
                           result = i;
                           break; 
                       }
                   }
                   return result;
               };
           }
      ```

    * ```
      function unique1(arr){
          var newArr = [];//新建一个数组
          for(var i=0; i<arr.length; i++){
              if(newArr.indexOf(arr[i]) == -1){//若新数组中未包含该项则将其存入新数组
               newArr.push(arr[i]);
           }
          }
          return newArr;
      }
      ```

  * 2.数组下标去重法

    * 思路: 如果当前数组的第i项在当前数组中第一次出现的位置不是i,那么表示第i项是重复的,忽略掉。否则存入结果数组

    * 注意: 也用到了`indexOf`

    * ```
      function unique2(arr){
          var newArr = [];
          for(var i=0; i<arr.length; i++){
               if(arr.indexOf(arr[i]) == i){
                   newArr.push(arr[i]);
               }
           }
           return newArr;
      }
      ```

  * 3.排序后相邻去重法

    * 思路: 将传入的数组进行排序,相同的元素就会相邻。再遍历数组,将元素与新数组的最后一个值进行比较,若不同则加入新数组

    * ```
      function unique3(arr){
           arr.sort();
           var newArr = [arr[0]];
           for(var i=1, len=arr.length; i<len; i++){
               if(arr[i] !== newArr[newArr.length-1]){
                   newArr.push(arr[i]);
                  }
           }
           return newArr;
      }
      ```

  * 4.优化遍历数组

    * 思路: 遍历传入的数组,元素与右边元素依次比较,若元素有重复,则结束当前元素的比较,将下一个元素当做比较对象,即跳出内层循环

    * ```
      function unique4(arr){
           var newArr = [];
           for(var i=0,len=arr.length; i<len;i++){
               for(var j=i+1;j<len;j++){
                   if(arr[i] === arr[j]){//获取没重复的最右一值放入新数组
                       ++i;
                   }                 
               }
               newArr.push(arr[i]);
           }
           return newArr;
      }
      ```

* **引申:合并数组并去重**

  * 一.`concat()`方法

    * 思路: `concat()`方法将传入的数组或非数组值与原数组合并,组成一个新的数组并返回。该方法会产生一个新的数组

    * ```
      function concatArr(arr1, arr2){
          var arr = arr1.concat(arr2);
          arr = unique1(arr);//再引用上面的任意一个去重方法
          return arr;
      }
      ```

  * 二.`Array.prototype.push.apply()`

    * 思路: 不会产生一个新的数组

    * ```
       var a = [1, 2, 3];
       var b = [4, 5, 6];
       
       Array.prototype.push.apply(a, b);//a=[1,2,3,4,5,6]
       //等效于:a.push.apply(a, b);
       //也等效于[].push.apply(a, b);
       
       
       
       function concatArray(arr1,arr2){
           Array.prototype.push.apply(arr1, arr2);
           arr1 = unique1(arr1);
           return arr1;
       }
      ```

### 23.   前端框架,优缺点,以及在使用过程中遇到的一些难点和解决方法

**http://www.css88.com/archives/7559**

* `Jquery`
* `Zepto`
* `Font Awesome`
* `Bootstrap`
* `Vue`
* `Angular`
* `Angular 2`
* `React`
* `Node`
* `Ajax`
* `npm,yarn`
* `Webpack`
* `Babel`
* `ESLint`
* `Redux`





### 24. 请以优雅的方式求出该数组前10个元素之和

```
var arr = [1,2,3,4,5,6,6,7,8,9,10,11,12,13,14,15]
var num=0;

for(var i=0;i<10;i++){
  num+=arr[i];
}
console.log(num)//51
```





###25.   `vue`的声明周期是怎么运转的