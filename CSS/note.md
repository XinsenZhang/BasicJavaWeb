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
        * 给父元素添加浮动
    