## CSS

###  CSS

**网页布局第一准则：多个块级元素纵向排列找标准流，多个块级元素横向排列找浮动。**

* CSS属性书写顺序

  >![image-20210415201419249](C:\Users\tracy\AppData\Roaming\Typora\typora-user-images\image-20210415201419249.png)

* 嵌入CSS样式有三种方式

  * 第二种是

    > 写在style中。
    >
    > 对于标签选择器如div、input都是，对于div格式：
    >
    > ```css
    > div{
    >  background-color: ;
    > 
    > }
    > ```
    >
    > id选择器,如id="hh"，格式
    >
    > ```
    > #hh{
    > (单独对某个id的进行样式的设计)
    > }
    > ```
    >
    > 类选择器，主要是用于CSS，对同一class的标签设置样式。（id是每个节点都不同的，所以两者不一样）**优先级最高**
    >
    > ```
    > .class名{
    > 
    > }
    > ```

  * 写外面文件上，直接引入

    ```
    <link rel="stylesheet" type="text/css" href="css/1.css"/>
    ```

* 各类标签

  * 关于文本样式：

    > 行内元素或行内块元素水平居中给其父元素添加text-align：center

  * ：hover设置鼠标悬停时的样式，对文字和边框都支持（：的左右都不许有空格）

  * border属性：style类型solid实线dashed虚线dotted点线，常用的还有width和color（复合写法有，四个边框都可以单独设置）

    > 对于表格其实就是很多小单元格组成，在设置border时，因为是两个单元格合并，所以边框变粗了，使用border-collapse：collapse属性控制相应单元格的边框

  * 内边距、外边距（内补丁、外补丁）

    > ​       对于内补丁，padding-top相关，就是在自己的块内打补丁，padding-left相当于在块内左边打补丁，即左边空出来一块，也相当于把该div内的块右移。

  >对于导航条，文字数量不一样，可以用padding控制每个的边距相同
  >
  >规定了width对于左右就会撑开，不然不会撑开（*如：盒子设置了height，没设置width，那么对于左右，可以根据padding设置居中，通过margin设置上下间隔*）
  >
  >![image-20210412204446396](C:\Users\tracy\AppData\Roaming\Typora\typora-user-images\image-20210412204446396.png)
  >
  >​      对于外补丁margin-top，就是对于该块在外面打补丁了。
  >
  >​      外边距可以让块级盒子水平居中，但是必须满徐两个条件：盒子指定了宽度、盒子的左右外边距都设为auto。对于两个嵌套关系的块元素，父元素和子元素都有上边距的情况下，父元素会塌陷较大的外边距值（对标准流来讲，只在父子之间存在，两个同级之间不会存在），因为本来他们两个块是贴在一起的，解决办法，给父级块加个padding（把其和子的隔开），或给父元素定义上边框，可以为父元素添加overflow:hidden

  * 图片浮动：float

  * 定位position，可对块在页面的位置根据left、right等进行绝对定位

  * cursor属性可以改变光标的样式（设置成无法点击等状态）

  * 后代选择器：ol（父级）li（子级）{ }

    .nav ul li {   }

  * .nav>a仅仅选择了该类的子标签，孙子就不要了

  * 链接伪类选择器。为确保生效，应按照LVHA的顺序声明，给链接指定样式，一般要单独指定，一般都是定义一个普通的标签a对其设置样式，再定义它的hover

  * ：focus把获得光标的标签元素取出来如，input：focus

    ![image-20210411210504999](C:\Users\tracy\AppData\Roaming\Typora\typora-user-images\image-20210411210504999.png)

  * p标签和div标签是兄弟标签，p标签里面主要用于放文字，不能放块级元素（都是块级元素），只有块级元素才能设置宽高等。

  * 对于行内元素，特殊情况链接a标签里面可以放块级元素

  * 行内块元素：input、img等他们是一行可以有多个的，但是可以设置宽高内边距等。

* 显示模式的转换：比如a标签是行内标签无法设置宽高，但很多情况下，需要他是一个块的形式，可以改变其样式，dispaly：block转换为块级元素；块级转换为行内元素，display：inline；转换为行内块元素（行内块元素的特点宽在没定义的情况下，根据内容来，两个盒子之间有空隙！），display：inline-block。*（经转换不是把是否在一行显示改了，而是是否可以设置宽高，根据是否能一行显示就应该把行或者块元素选好*）

* a标签是盒子，是样式对其设置height设置的是盒子的高度，若要设置其中的文字让其垂直居中，应使用line-height=height，行间距其实是文字高度加上上下的间隙之和，当这个值小于height文字会在盒子的靠上面显示 ，大于则在靠下面显示。行高会继承给孩子。

* font: 15pt/17pt bold "Arial" normal 

  > 文字大小/行高，行高可以不带单位，那就是指倍数
  >
  > font-weight为400时是normal程度，文字不加粗
  >
  > 对文字的斜线形式、下划线等都是font-style
  >
  > 调文字的时候，最好是文字在哪个标签内部，就调哪个。

* 背景图片：用于logo、装饰性小图片（对比直接插入img，它便于控制位置）

  * background-image：none|url（图片）

    > 关于url，若是同文件夹，直接写，若不是，从根目录开始，即../

  * background-repeat：背景图平铺的方式，沿x、y轴等

  * background-position：x，y（若为具体的数值，则左边是x轴方向上的值，右边是y轴方向上的值，仅给定一个，则另一个默认居中），水平靠上center top或top center都可以，即与顺序无关。

  * background-attchment：固定或滚动（滚动是默认状态，网页下拉时，也能看到图片的下面部分）

  * 可以把这些属性合写在一起，

    > 当使用简写属性时，没有特定的书写顺序，一般约定为：

  >`颜色 图片地址 背景平铺 图像滚动   背景图片位置`

    ```css
  background:black url(image.jpg) repeat-y fixed top
    ```

  * 背景色透明写法

    > 不影响盒子里面其他内容

    ```
    background:rgba(0,0,0,0.3)		
    ```


* 三大特性：

  * 样式冲突时，利用就近原则

  * 继承性，子元素继承父元素的部分样式（text-、font-、line-这些元素开头的可以继承，以及color属性）

  * 优先级，从父类继承过来的权重为0，若在样式上加！important则优先级最大（复合选择器会有权重叠加）

  * 并集选择器就是在两个选择器之间加，对他们进行相同的样式设计，避免写过多重复的代码

  * 和浏览器一样宽的盒子不用设置宽度

  * 在开始设计样式时首先清除原本的样式

    ```
    *{ 
        padding:0;
        margin:0;
    }
    ```

    

* 关于使用不同盒子的小tips：

  * 标题用h标签，大量文字段落用p

* 圆角边框

  > border-radius：length
  >
  > 长度可以实具体的例如10px，也可以是百分比，其中四个角可以是不同的圆角。

* 盒子阴影

  > box-shadow：**h-shadow**（水平方向，可正可负） **v-shadow**（垂直方向，可正可负） blur （模糊程度，阴影的虚实）spread（阴影大小） color（一般用rgba透明度） inset（默认是外阴影outset若要改变成内阴影改为inset）

* 文字阴影：text-shadow

* 浮动（如让多个块级盒子**水平排列成一行**，虽行内块元素可以实现，但块间有缝隙，难控制；左右对齐等）：**创建浮动框，将其移动到一边，直到左边缘或右边缘及包含块或另一个浮动框的边缘。**

  > 选择器{ float：none|left|right；}
  >
  > **特性：浮动的元素脱标；浮动的盒子不再保留原先的位置（他们不占标准流的位置）；浮动的元素具有行内块元素的特点**
  >
  > 为了约束浮动元素的位置，先用标准流的父元素排列上下位置，之后内部子元素采取浮动排列左右位置。
  >
  > 关于标准流和浮动的覆盖问题:1  第一个块是浮动，第二个是标准流，第一个就会脱标，第二个来顶替他的位置就会覆盖。2 第一个块是标准流，第二个是浮动的，他会左上角以第一个块的左下角为起始开始布局，因为对标准流的div来说它是独占一行的。（只会压住盒子，不会压住下面标准盒子里面的 文字，比如图片浮动，文字可以环绕在它周围）

    * 清除浮动：父级盒子不方便给高度时，浮动盒子不占位置，使其高度为0，对后续标准流的排版有影响。

      > 选择器{clear：left|right|**both**}

      1. 额外标签法

         > 在浮动的盒子后面加个**块级**标签，并给一个style清除浮动

      2. 父级添加overflow属性

         >父级盒子添加overflow属性，将其属性值设置为hidden、auto或scroll

      3. 父级添加after伪元素

         ```css
         /*类名加在标签原本的类名之后，用空格隔开*/
         .clearfix:after{
              content:".";        
              display:block;        
              height:0;        
              clear:both;        
              visibility:hidden;        
         
         }
         /*为了兼容IE6、7*/
         .clearfix{
               zoom:1
         }
         ```

         

      4. 父级添加双伪元素

         ```css
         .clearfix:before,
         .clearfix:after {
         content: "";
         display: table;
         }
         .clearfix:after {
         clear: both;
         }
         /* ie6 7 专门清除浮动的样式*/
         .clearfix {
         *zoom:1;
         }
         ```

* 定位position（可以让盒子在某个盒子内~~一佛那个~~或固定在屏幕中某个位置，且可以压住其他盒子）

  >**定位=定位模式+边偏移**
  >
  >定位模式：static（静态定位）、relative（相对定位）、absolute（绝对定位）、fixed（固定定位）
  >
  >边偏移：定位的盒子移到最终位置，有top、bottom、left和right四个属性
  >
  >属性值为具体的数值如top：80px，顶端偏移量，定义元素相对于其父元素上边线的距离。	

   * 静态定位static：元素的默认定位方式，意思就是无定位

     > 选择器{position：static；}
     >
     > *静态定位*按照*标准流*特性摆放拜访，无边偏移

   * **相对定位**relative

     > 特点：它的移动位置参照它以前的位置；
     >
     > ​            原来在标准流的位置继续占有，后面的盒子仍然以标准流的方式对待它。（不脱标，继续保留原来位置）

    * **绝对定位**absolute

      > 绝对定位是元素在移动位置的时候，是相对于它祖先元素来说的。
      >
      > 特点：如果没有父元素或父元素没有定位，则以浏览器为准定位
      >
      > ​            如果祖先元素有定位（相对、绝对、固定定位），则以最近一级的有定位祖先元素为参考点移动元素。
      >
      > ​            绝对定位不再占有原先的位置（脱标）           

    * **固定定位**fixed

      >固定定位是元素固定于浏览器可视区的位置。（页面滚动时，其位置不会改变）
      >
      >特点：以浏览器的可视窗口（浏览器边界）为参照点移动元素。（没有父元素，即使页面滚动，它的位置不会变）
      >
      >​            不再占有原先的位置。（可看作一种特殊的绝对定位）
      >
      >小技巧：固定在版心的右侧位置
      >
      >​    小算法：让固定定位的盒子left：50%。走到浏览器可视区（版心的一半）；让该盒子margin-left：版心宽度的一半距离

    * 粘性定位sticky

      > 粘性定位被认为是相对定位和固定定位的混合。
      >
      > 特点：以浏览器的可视窗口为参照点移动元素（固定定位特点）
      >
      > ​            粘性定位占有原先的位置（相对定位特点）
      >
      > ​            必须添加top、left、right、bottom其中一个才有效

  * 定位叠放次序z-index（只有定位的盒子才有这个属性）

    > 在使用定位布局时，可能会出现盒子重叠的情况。使用z-index来控制盒子的前后次序（z轴）
    >
    > 选择器{z-index:1;}数值可以是正整数、负整数或0，默认auto，数值越大，盒子越靠上。若属性值相同，则按照书写顺序，后来居上

  * 定位的拓展

    > 绝对定位的盒子居中：加了绝对定位的盒子不能通过margin：0 auto水平居中，可以通过以下计算方法实现。
    >
    > 小算法：left走50%，即父容器宽度的一半；用margin负值，往左边走自己盒子宽度的一半。
    >
    > 对于行内元素：添加了绝对或固定定位，可以直接设置高度和宽度
    >
    > 对于块级元素：添加了绝对或固定定位（脱标），如果不给宽度或者高度，默认大小是内容的大小。

  * 

* 导航栏：实际开发中，我们不会直接用链接a而是用li 包含链接（li+a）的做法

  > 导航栏一般写法：ul>li>a(导航栏横在排列，是给li加浮动，因为a是行内标签本就是一行显示)，在网页中的链接若都不需要下划线，直接对a标签修改。
  >
  > 导航栏的布局的修改，直接对a进行修改，不需要使用li。
  >
  > 导航栏可以不用给宽度，因为文字可能会增加。
  >
  > 利用padding来控制两个a之间的距离

* 搜索栏

  > 按钮button默认有个边框

* img标签

  > 当图片和块不一样大小时，设置width：100%

* 多个图片轮播的导航条，做法：用li，先删除它们的样式，给每一个li设置宽度和高度，然后设置border使其变成小圆圈。

* 元素的显示和隐藏

  * display属性：用于设置一个元素应如何显示

    >display：none；隐藏对象（隐藏后，不再占有原来的位置）
    >
    >display：block；除了转换为块级元素以外，还有把元素显示出来的意思

  >display：table；转换为块级元素并且一行显示

  * visibility可见性

    > visibility：visible；元素可视

  >visibility：hidden；元素隐藏（隐藏后，继续占有原来的位置）

  * overflow溢出

    > overflow：visible
    >
    > overflow：hidden（有些有定位的盒子，就不能用，会隐藏多余的部分）

  >overflow：scroll（有滚动条）
  >
  >overflow：auto（超出了就显示滚动条，没有超出就不显示）

* CSS精灵技术（sprites）：有效减少服务器接收和发送请求的次数，提高页面的加载速度

  > 主要针对于一些背景图
  >
  > 移动的是背景图片的位置，使用background-position
  >
  > 移动的距离就是这个而目标图片的x、y坐标
  >
  > 使用精灵图时需要精确测量，每个小背景图片的大小和位置ziti tubi

* 字体图标（iconfont）

  > 总结：如果遇到一些结构和样式比较简单的小图标，就用字体图标（是字体，可以改变大小颜色）
  >
  > ​            如果遇到一些结构和样式复杂一点的小图片，就用精灵图
  >
  > 网站：icomoon.io或者阿里iconfont字库
  >
  > 引入：1.在网上下载后，把fonts文件夹放入页面根目录（fonts文件夹中文件有四种格式，是因为不同的浏览器所支持的字体格式不一样）；2.在CSS样式中全局声明字体：简单理解把这些字体通过css引入页面中（在style.css的第一段）；3.html的span标签内添加小图标（去找小图标的网站找了写，或者直接写\e924等）
  >
  > 追加新的小图标：点击import icons，选择selection.json，选择新的小图标，然后生成。

* 三角制作

  >在盒子宽高都设置为0的情况下，设置其他三个边框都为透明色（transparent）。
  >
  >为了照顾兼容性，加line-height:0,font-size:0
  >
  >任意直角三角形的制作：长直角边设置边框宽度，小锐角在的边设置边框大宽度，其他设置为0。如，长边朝左，小边朝上的小三角
  >
  >```css
  >border-color: transparent transparent transparent red;
  >border-style: solid;
  >border-width: 0 0 22px 8px;
  >```
  >
  >秒杀做法：一个大盒子，里面分为两部分，但不需要两个盒子，因为都是文字，把左边设为一个盒子，让它浮动，右边的文字自然iu环绕它了，然后在第一个块里面加绝对定位的小三角

* CSS用户界面样式

  * 鼠标样式cursor

    >li{cursor：pointer}
    >
    >属性值：default ：小白（默认）pointer： 小手    move：移动   text：文本
    >
    >not-allowed：禁止

  * 轮廓线outline

    > 给表单添加outline：0；或者none；样式之后，就可以去掉默认的蓝色边框。
    >
    > input{outline：none} （在输入时，框框会变蓝）

  * 防止拖拽文本域resize

    > textarea{
    >
    > ​      resize：none
    >
    > }

  * vertical-align属性应用

    > 使用场景：经常用于设置图片或者表单（行内块元素）和文字垂直对齐（行内元素或行内块元素）
    >
    > 属性值middle中线对齐，top顶部对齐，bottom底端对齐，baseline是和字母的最底端对齐。
    >
    > 解决图片底部默认空白缝隙问题：（bug：图片地测会有一个空白缝隙，原因是行内块元素会和文字的基线对齐）直接给图片添加vertical-align；或者把图片转换为块类型，这样就不会有跟基线对齐这种问题了

  * 溢出的文字省略号显示

    * >单行显示省略号：
      >
      >> 必须满足三个条件：1.先强制一行内显示文本white-space：nowrap；*说明：normal是默认的，如果文字显示不开自动换行，而nowrap是强制在一行显示*
      >
      >> 2.超出的部分隐藏overflow：hidden
      >
      >> 3.文字用省略号替代超出的部分text-overflow：ellipsis
      >
      >多行显示省略号
      >
      >```
      >display: -webkit-box;
      >-webkit-box-orient: vertical;
      >-webkit-line-clamp: 3;
      >overflow: hidden;
      >text-overflow：ellipsis
      >```

  * margin负值的应用

    > 淘宝网中每个商品的盒子都挨在一起，也都有边框，如何控制边框不重叠？
    >
    > 把每个盒子都加上margin的负值（值是边框大小）！可以覆盖
    >
    > 覆盖后，一般有悬浮在块上的变色效果，呗压住的边显示不出来颜色如何解决？
    >
    > 加相对定位，相对定位的盒子不会被标准流的压住；或者修改z-index，让它在最上层显示

  * 行内块运用

    > 对于行内元素或者行内块元素，水平居中直接用text-align：center

    

### CSS3新特性

* 属性选择器

  * 利用属性选择器就可以不用借助于类或者id选择器

    > input[value]：即有value属性的input标签
    >
    > input[type=text]：选择属性=值的某些元素
    >
    > input[class^=icon]：选择的首先是div，然后具有class属性，并且属性值必须是icon开头的这些元素
    >
    > input[class$=icon]：选择的首先是div，然后具有class属性，并且属性值必须是icon结尾的这些元素
    >
    > input[class*=icon]：选择的首先是div，然后具有class属性，并且属性值中必须含有icon的这些元素

  * 对于class=“icon1”的div，在设计样式时，也能写为div.icon1（这是个div且属性名叫icon1）

* 结构伪类选择器（根据文档结构来选择）

  > E：first-child  匹配父元素E中的第一个子元素
  >
  > E：last-child  匹配父元素中的最后一个子元素
  >
  > E：nth-child（n） 匹配元素中的第n个子元素E（选择一个或多个特定的子元素）
  >
  > E：first-of-type 
  >
  > E：last-of-type
  >
  > E：nth-of-type（n）
  >
  > 两者区别：对于child，把所有的孩子排序，执行的时候先看：后面的，然后去看前面它是什么标签，存在匹配不上的情况；而type会把指定类型的盒子排上序号，再做匹配选择，找第n个孩子

  * 关于nth-child（even|odd）可以对第偶数个或奇数个元素做操作。
  * nth-child（n）不写具体的数值直接写n就是选择了所有的孩子
  * n可以是公式，如：2n、5n、n+5、-n+5（前5个）

* 伪元素选择器（利用css创建新的标签，不再html中显示，简化结构）

  > element：：before{}     在元素内部的前面插入内容
  >
  > element：：after{}     在元素内部的后面插入内容
  >
  > 新创建的这个元素在文档中是找不到的，所以称之为伪元素（属于行内元素）
  >
  > before和after必须有content属性
  >
  > 它们的权重和标签选择器一样，为1

  * 使用场景：iconfont、土豆的mask、清除浮动

* 盒子模型

  > 通过box-sizing来指定盒模型，默认为content-box，而修改为border-box的话就不会因为padding而撑开盒子了

* CSS3过渡（谁做过渡给谁加）

  > transition：要过渡的属性 花费时间 运动曲线 何时开始
  >
  > 属性：想要变化的css属性，宽高 背景颜色 边距等（多个属性变化直接用all）
  >
  > 花费时间：单位是秒
  >
  > 运动曲线：默认是ease（可以省略）
  >
  > 何时开始：单位是秒，可以设置延迟触发时间  默认0s（可以省略）