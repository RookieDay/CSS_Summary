1.图标引入
    网站名/favicon.ico     都可以下载到所有网站的图标
    引入图标 比如www.jd.com/favicon.ico
    1.	<link rel="shortcut icon" href="favicon.ico">
    2.	bitbug.net这个网站中有这句话
        a)	<link rel="shortcut icon" href=" /favicon.ico" /> 绿色部分要删掉
2.小标签（s,del,em,I,u,ins…）我们做一些小的效果图，会很青睐他们
    Font: 400 12px/12px “宋体”;     加粗，大小，行高，格式；（不行高，默认为0）。
    s   del   :    删除线
    em  I     :     倾斜
    uins      :     下划线
    outline-style: none;       清除外边线（蓝色）
    text-decoration: none;    清除下划线，删除线。
    Resize : none;    文本框禁止拖拽。
    Font-weight: normal;      加粗变正常
    Font-style: normal;       倾斜变正常。
3.
  内外边距问题
    Padding:  可以加背景色。
    Margin： 不可以加背景色的。
    Border:   不可以加背景色的。（你可以单独给他加边线的颜色）
  行高和高度
    行高：文字的高度。（给父盒子行高，子盒子不会有高度）
    高度：盒子的高度。（给父盒子加高度，子盒子不继承。宽例外）
  盒子稳定性
    宽高：最稳定的。
    Padding：比较稳定。（里面不能放内容，背景图除外）
    Margin：最不稳定。（1.不能放内容。2不能加背景。3.容易出现外边距合								并）     优点：用起来比较方便。
  居中问题
    盒子左右居中      Margin： 0 auto;
    盒子上下居中      （父盒子给padding,  子盒子给margin。 定位）    

    文字左右居中：   1.text-align:center;     2.paddign:  0   10px;
    文字上下居中：   1.line-height:  盒子的高度。   2.。。。
  模拟鼠标
    Cursor :    pointer;             鼠标变成小手
    Cursor :    text;                鼠标变成插入条光标
    Cursor :    move;              鼠标变成四角箭头
    Cursor :    default;             鼠标变成白色箭头
  小知识
    背景图不会撑开盒子。
    图片和文字会撑开盒子。（文字比较特殊）
    在小标签（行内标签）的情况下：定位之后，不写left属性，默认的地方会出现的padding和a链接中的文字之后。
  圆角矩形
    border-radius:   1em;
    border-radius:   50%;
    border-radius:   宽高一半（px）;
    border-radius:   左上角  右上角  右下角  左下角;

  清除浮动：
    原因：父盒子高度为0，子盒子不占位置。
    清除浮动目的：让父盒子有高度。
    解决办法：
        a. clear: both ; 看图一
        b. overflow: hidden ( 缺点：超出盒子的部分会被隐藏) 看图二 
        c. 单伪元素标签法
            .clearfix:after {
                content: “”;
                height: 0;
                visibility: hidden;
                overflow: hidden;
                display: block
                clear: both;
            }
            .clearfix {
                *zoom: 1; /*兼容IE678*/
            }

        d.双伪元素标签法
            .clearfix:after ,.clearfix:before {
                content: “”;
                display: table;
            }
            .clearfix:after {
                clear: both;
            }
            .clearfix {
                *zoom: 1; /*兼用IE678*/
            }

  盒子居中
    左右居中：1.给盒子absolute定位，left=50%；
             2.让盒子移动。 Margin-left: -自身宽度一半。
    上下居中：1.给盒子absolute定位，top=50%；
             2.让盒子移动。 Margin-top: -自身高度一半。
    操作：定位—>absolute。
        左右居中： left：50%；      margin-left: 负盒子自身宽一半
        上下居中： top： 50%；     margin-top：负盒子自身高一半。

  左右移动盒子
    Margin正值的情况下。指的是给盒子外边距。
    Margin负值的情况下。反方向移动盒子。（margin-left ： margin-top）
  继承问题
    宽度会被继承
    行高会被继承
    高度不会被继承
    文字居中（text-align:center）可以被继承
  浮动问题
    不管两个盒子之间的关系是什么。只要不是父子关系。
    他们相互都会受到浮动的影响。
    解决方法：让子盒子，浮动的子盒子，不要超出父盒子。
  Li和a的关系
    如果鼠标放到空白处a链接变色，说明a链接撑开的li 。
    如果鼠标放到空白处a链接不变色，说明li包含的a链接 。
  属性冲突问题
    定位中的left和right不冲突。以left为准。
    定位中的top和bottom不冲突。以top为准
  半透明
    opacity: 0.5；   他可以让盒子半透明。（缺点：就是内容跟着一起半透明）
    background：rgba(255,255,255,0.5);   C3透明度用法。
    background：rgba(255,255,255, .5);    C3透明度用法。
  界面跳转
    a 链接如果不想跳转，方法如下
      javascript:;            <a href=”javascript:;”></a>
      javascript:void(0);     <a href=”javascript:void(0);”></a>
  宽度继承
    是在加上padding值之后，和宽度的总和，等于父盒子的宽度。
  层级
    层级和占不占位置没有关系。（relative本身就是站位置的）
    层级可以继承（拼爹）。（浮动和定位都是不能继承的）
    定位的盒子是最高的。（相比的是标准流和浮动的盒子。）
    只有定位的盒子才有层级。
    如果都有定位，后续的盒子会压住前面的盒子。
