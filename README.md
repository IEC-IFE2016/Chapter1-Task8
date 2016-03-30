# Chapter1-Task8-vizards
> 百度IFE - 第一阶段 - 任务8 - 响应式网格（栅格化）布局

### 任务描述
- 需要实现如下图所示，调整浏览器宽度查看响应式效果，效果图中的红色的文字是说明，不需要写在HTML中。
  ![效果图](http://7xrp04.com1.z0.glb.clouddn.com/task_1_8_1.png)
- 网格布局的作用在于更有效地控制元素在网页中所占比例的大小。比如，博客中有一个留言板模块，在比较大的屏幕上，我们希望它占了右边25%的宽度，在手机等比较小的屏幕上，我们希望它占100%的宽度，出现在博客文章下方。网格布局是一种实现这一需求的办法，它的好处是，把所有的宽度分为固定栏数（常用12栏），从而更高效的控制元素宽度。而这功能，我们使用HTML和CSS就能实现了。
- 以BootStrap的网格系统为例，DOM元素类名形如```col-md-4```；其中```col```是“列”column的缩写；```md```是medium 的缩写，适用于应屏幕宽度大于 768px 的场景；```4```是占四栏的意思。因此，```col-md-4```的意思是，在屏幕宽度大于768px时，该元素占四栏。  

### 参考资料
- [BootStrap 官网](http://www.bootcss.com)：如果你没用过的话，至少了解一下它是做什么的
- [Bootstrap grid examples](https://getbootstrap.com/examples/grid/)：改变浏览器宽度，查看不同类名元素的表现，理解网格系统的作用。然后，通过“审查元素”查看对应 CSS，思考这一系统是如何实现的
- [BootStrap 带 offset 的网格系统](http://getbootstrap.com/2.3.2/scaffolding.html#gridSystem)
- [Creating Your Own CSS Grid System](http://j4n.co/blog/Creating-your-own-css-grid-system)：你可以先自己想想怎么实现，没有思路的话看看别人的做法

### 实现总结
1. 主要使用了响应式布局中的媒体查询，应题目要求以768px为关键宽度进行适配
2. 通过学习bootstrap源码，使用了一种新的CSS选择器：```[class*="col-"]```或```[class^="col-"]```
  - ```[class*="col-"]```表示所有以`col`开始的类都使用这个规则
  - ```[class^="col-"]```表示类名中含有```col-```的类都使用这个规则
  
  有着正则的意味。stackoverflow上对这种选择器的解释如下：

  > You could use ```[class*="col-"]``` CSS attribute selector to select any element contains at least one occurrence of ```col-``` as its ```class``` value.
    ```
    [class*="col-"] {
        border-color: red;
    }
    ```
    If all values of ```class``` attributes begin with ```col-```, you could use ```[class^="col-"]``` selector.
    However, in order to prevent for classes like ```foo-col-1``` to be selected, you could use a combination of two above selectors as follows:
    ```
    [class^="col-"], [class*=" col-"] {
        border-color: red;
    }
    ```

### 任务完成情况
- [x] 代码实现
- [x] 任务总结
- [x] 任务提交    
    
