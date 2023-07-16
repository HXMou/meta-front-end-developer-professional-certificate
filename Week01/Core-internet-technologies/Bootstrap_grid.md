## 机制原理

*   栅格断点的媒体查询基于宽度的 *最小值*，意味着它们 __应用到某一等级以及这一等级之上的所有__（如`.col-sm-4`的的定义可以在小型、中型、宽、超宽设备上呈现，但不适用于能在超小型`.col-sx`上呈现）。

*   `.col-*`后面有不同的数字，如`.col-sm-4`或`.col-xl-12`，这些css类后面的数字用于表明定义div空间想要占用列的数量，每行最多有12列。如果你想用三个等宽的列，则取12的三分之一，即`.col-sm-4`就是正确的(后文会有详细的介绍)。
    
*   `.col-*`的`width`属性(即列宽)是用百分比来表现和定义的，所以它们总是流式的，其尺寸大小受父元素的定义影响(这正是`flexbox`布局的特征，子元素的宽比和排列受父元素定义)。
    
*   列具有水平`padding`定义，用于创建列与列之的间隙。
    
*   `.row`上带有`margin-left: -15px;margin-right: -15px;`属性，你可以在`.row`上上定义`.no-gutters`属性，从而消除这个属性，使页面不会额外宽出30px，即`<div class="row no-gutters"...`。(译者原意拆成两行表述)。
    
*   总共有[五个栅格等级](https://getbootstrap.net/docs/layout/grid/#responsive-breakpoints)，每个响应式分界点隔出一个等级：特小`.col`、小`.col-sm-*`、中`.col-md-*`、大`.col-lg-*`、特大（大、特大也可以称为宽、超宽）`.col-xl-*`。
    
## 自动布局列

利用栅格断点特性进行排版，可以简化列的大小，而不需要批定显式的列宽，如强制写为：`.col-sm-6`。

## 等宽布局

从`xs`（如上表如见，实际上并不存在xs这个空间命名，是以`.col`表示，下同不再注）到`xl`（即`.col-xl-*`）所有设备上都是等宽并占满一行，只要简单的应用`.col`就可以完成。

## 响应式的class选择器[](https://getbootstrap.net/docs/layout/grid/#responsive-classes)
-----------------------------------------------------------------------------
 
Bootstrap的栅格系统包括五种宽带预定义，用于构建复杂的响应布局，你可以根据需要定义在特小`.col`、小`.col-sm-*`、中`.col-md-*`、大`.col-lg-*`、特大`.col-xl-*`五种屏幕(设备)下的样式。
 
## 覆盖所有设备[](https://getbootstrap.net/docs/layout/grid/#all-breakpoints)
 
如果要一次性定义从最小设备到最大设备相同的网格系统布局表现，请使用`.col`和`.col-*`类。后者是用于指定特定大小的(如`.col-6`)，否则使用`.col`就可以了。

## 混合布局

    <!-- 定义在超小屏幕下1列全宽、1列半宽，而其它场景以8:4比例并行排列 -->
    <div class="row">
    <div class="col-12 col-md-8">.col-12 .col-md-8</div>
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
    </div>

    <!-- Columns start at 50% wide on mobile and bump up to 33.3% wide on desktop -->
    <div class="row">
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
    </div>

    <!-- Columns are always 50% wide, on mobile and desktop -->
    <div class="row">
    <div class="col-6">.col-6</div>
    <div class="col-6">.col-6</div>
    </div>