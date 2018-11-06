# note on css
* lecture 1 格式及介绍
    * 样式属性:样式值;
	* {样式属性:样式值;  样式属性:样式值;}
	* css选择器{样式属性:样式值;  样式属性:样式值;}
	* 内联样式,仅对当前有用
	* 外联样式单独一个文件和定义在head中其实一样
	* 内联样式的优先级要高于外联样式

* lecture 2 CSS常见选择器和CSS中的伪元素
    * 常见选择器
        * ID选择器
            *  id唯一不可重复
            * 用的比较少
        * 元素选择器
        * 类(class)选择器
        * 属性选择器
	* 伪类选择器
	    * 所有的伪类签都要加上冒号
	    * :link
	        * 向未被访问的连接添加样式
	    * :hover
	        * 当鼠标悬浮在元素上方时,向元素添加样式
	    * :active
	        * 向被激活的元素添加样式
	    * :visted
	        * 向已访问的链接添加样式
	* 伪元素
	    * 前面要加两个冒号::
	    * 虚拟是因为html源代码里没有,开发者审查里面有
	    * ::before
	        * 会为当前元素创建一个子元素作为伪元素,这个元素是虚拟的,作为第一个元素出现
	    * ::after
	        * 用来匹配已选中的元素的一个虚拟的最后子元素
	* 优先级
	    * id选择器 > 类选择器和属性选择器 > 元素选择器和伪类
	    * 加上!important 可以把当前选择器的优先级别提到最高,比内联选择器还要高

* lecture 3 CSS设计样式
    * 背景样式属性
    * 背景 background
        * background
            * 简写属性,作用是将背景属性设置在一个声明中
            * 简写属性的意思是可以编写以下四种属性
        * background-color
            * 设置元素的背景颜色
        * background-image
            * 把图像设置为背景
            * 设置的是一个本地或者互联网上的url
            * url()
            * 可以设置参数
                * height
                * width
        * background-position
            * 设置图像的起始位置
            * 后面跟着两个值作为一组参数.-x,-y
                * 将原来的图像左移x 个px
                * 将原来的图像上移y 个px
        * background-repeat
            * 设置图像是否及如何重复
            * 一般是四个值
                * repeat
                * no-repeat
                * repeat-x
                * repeat-y
    
    * 文本样式属性
    * text文本
        * color
            * 设置文本颜色
        * text-align
            * 对齐元素中的文本
            * 水平方向
        * text-decoration
            * 向文本添加修饰
        * text-indent
            * 缩进元素中文本的首行
        * vertival-align
            * 设置元素的垂直格式
     
    * 字体的样式属性
    * 字体font
        * font
            * 在一个声明中设置所有的字体属性
        * font-family
            * 指定文本的字体系列
        * font-size
            * 指定文本的字体大小
        * font-style
            * 指定文本的字体样式
        * font-weight
            * 指定字体的粗细
    * CSS列表样式
        * list-style
            * 用于把所有用于列表的属性设置在一个声明中
        * list-style-image
            * 将图像设置为列表项标志
        * list-style-type
            * 设置列表性标志的类型
    
    * 表格样式
        * border
            * 简写属性
                * width 宽度
                * color 颜色
                * 样式 solid
        * border-colapse
        * width
        * text-aligh
        * padding
        
* lecture4 CSS布局
    * CSS的两行三列布局
    * CSS的三行两列布局
    
* lecture5 盒子模型
    * 外边距
    * 边框
        * bolder
        * bolder-width
        * bolder-color
        * bolder-style
    * 内边距
        * padding
            * 上右下左的顺序进行编辑
            * 与参数顺序有关
            * 全部
            * 上下和左右
            * 上,左右和下
            * 上,右,下,左
        * 边框也能这么设置
        * padding-bottom
        * padding-left
        * padding-right
        * padding-top
        
    * 外边距
        * margin
        * margin-top
        * margin-right
        * margin-bottom
        * margin-left

* lecture6 浮动属性
    * float的四个参数
        * float:left 
            * 左浮动
        * float:right
            * 右浮动
        * float:none
            * 继承浮动
        * float:inherit
            * 不浮动
    * float属性实现文本环绕效果
        * 原理: 使得元素成为块状元素
            * 比如span是一个内联元素,使用float能够显示 
        * 浮动元素虽然脱离了文本流,但是仍然占据文档空间
        * 后续文本会进行除了浮动元素之外的水平布局
    * float的原因及副作用
        * 产生浮动,脱离标准流
            * 比如两个同级别的div，浮动的会覆盖在非浮动的上方
        * 父元素无法准确定位
            * 父元素塌陷
            * 父元素的兄弟元素可能出现异常
            
    * 解决浮动副作用的四种方法
        * 手动设置高度
            * 父元素的宽度不够的时候子元素中的浮动元素会往下进行排列
        * 通过clear清楚内部的类和外部的类
            * clear:none
                * 不适用clear(默认)
            * clear:right
                * 不允许右边有浮动对象
            * clear:left
                * 不允许左边有浮动对象
            * clear:both
                * 两边都不允许有浮动对象
        * 给父元素添加overflow属性并结合zoom:1使用
            * overflow 是用来处理溢出的
                * 使用参数hidden 或者 auto都行
                * 弊端：
                    * 截断元素
            * zoom：1
                * IE里面的特性
                * 根据子元素的height来调整父元素的height
        * 给父元素添加浮动
            * 能够解决父元素塌陷的问题
            * 但是兄弟元素会受到影响
<<<<<<< HEAD
=======
    
* lecture 7 浮动属性实战
    * 实现慕课网的导航页浮动
* CSS 使用position进行定位
    * 又是一个模块又是一个属性
        * 模块
            * Positioned Layout Module
            * 提供与元素定位和层叠相关功能，它是核心模块
                * 盒子模型的类型和尺寸
                * 布局模型
                * 元素之间的关系
                * 视口大小，图像大小等其他相关方面
        * 属性   
            * .box{position:relative;}
    * CSS中的定位模型
        * position之static
            * 自然模型（静态模型/常规定位）
                * 定位中的一股清流，回归本真
                * 作用
                    使元素定位于常规/自然流中(块、行垂直定位下去，行内水平从左到右)
                * 特点
                    1. 忽略top,bottom,left,right或者z-index声明
                    2. 两个相邻元素如果都设置了外边距，那么最终外边距=两个外边距中最大的
                    3. 具有固定width和height值的元素，如果把左右外边距设置为auto，则左右外边距会自动扩大占满剩余宽度。造成的效果就是这个块水平居中
        * position之relative
            * 相对定位模型
                * 作用
                    * 使元素成为containing-block，官话是可定位的**祖先元素**
                        * 就是可以作为参照物
                * 特点
                    1. 可以使用top/right/bottom/left/z-index进行相对定位(相对的是谁？)
                    2. 相对定位的元素不会离开常规流--心念家乡
                    3. 任何元素都可以设置为relative,他的绝对定位的后代都可以相对于它进行绝对定位--超好用
                    4. 可以使浮动元素发生偏移，并控制它们的堆叠顺序
        * position之absolute
            * 绝对定位模型
                * 作用
                    * 使元素脱离常规流
                * 特点
                    1. 脱离常规流
                    2. 设置尺寸的时候要注意：百分比比的是谁？--最近的祖先定位元素
                    3. lrbt如果设置为0.**它将对齐到最近祖先可定位元素--衍生出一个居中妙计** margin设置成auto
                    4. lrbt如果设置为auto **它将被打回原形 恢复到常规流**
                    5. 如果没有最近定位元素，会认\<body\>做dady
                    6. z-idnex可以空着堆叠顺序。（999999见过吗？没有欸）
        * position之fixed
            * 固定定位模型
                * 作用
                    * 我跟绝对定位本是同根生，相煎何太急
                * 特点
                    1. 和absolute有啥区别？**the relative element of the absolutive positon**
                    2. 固定定位元素不会随着视口滚动而滚动
                        * 视口是指用户肉眼可见的文档的位置
                    3.  继承absolute的特点
                    4. 貌似只能对于body进行定位
        * position之sticky
            * 磁贴定位模型
                * 磁贴定位(粘性定位/吸附定位)--赛季新秀，实力布局糖
                * 作用
                    * relative+fixed的完美结合，制造出吸附效果
                * 特点
                    1. 如果产生偏移，原位置还会在常规流中，一亩三分地保留着
                    2. 如果它的最近祖先元素有滚动，那么他的偏移标尺就是近祖先元素
                    3. 如果最近祖先元素没有滚动，那么它的偏移标尺就是视口
                    4. 上下左右的偏移规则        
                    5. 不设置偏移量或者设置为auto,则就是relative
        * position之inherit
    * 使用定位模型来达到定位的效果
>>>>>>> windows
    