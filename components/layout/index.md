# Layout

- category: Components
- chinese: 布局
- type: 基本
- cols: 1

---

24 栅格系统。

## 设计理念

<div style="width:80%">
<div class="row demo-row">
  <div class="col-24 demo-col demo-col-1">
    100%
  </div>
</div>
<div class="row demo-row">
  <div class="col-6 demo-col demo-col-2">
    25%
  </div>
  <div class="col-6 demo-col demo-col-3">
    25%
  </div>
  <div class="col-6 demo-col demo-col-2">
    25%
  </div>
  <div class="col-6 demo-col demo-col-3">
    25%
  </div>
</div>
<div class="row demo-row">
  <div class="col-8 demo-col demo-col-4">
    33.33%
  </div>
  <div class="col-8 demo-col demo-col-5">
    33.33%
  </div>
  <div class="col-8 demo-col demo-col-4">
    33.33%
  </div>
</div>
<div class="row demo-row">
  <div class="col-12 demo-col demo-col-1">
    50%
  </div>
  <div class="col-12 demo-col demo-col-3">
    50%
  </div>
</div>
<div class="row demo-row">
  <div class="col-16 demo-col demo-col-4">
    66.66%
  </div>
  <div class="col-8 demo-col demo-col-5">
    33.33%
  </div>
</div>
</div>

在多数业务情况下，Ant Design需要在设计区域内解决大量信息收纳的问题，因此在 12 栅格系统的基础上，我们将整个设计建议区域按照 24 等分的原则进行划分。

划分之后的信息区块我们称之为『盒子』。建议横向排列的盒子数量最多四个，最少一个。『盒子』在整个屏幕上占比见上图。设计部分基于盒子的单位定制盒子内部的排版规则，以保证视觉层面的舒适感。

## 概述

布局的栅格化系统，我们是基于行（row）和列（col）来定义信息区块的外部框架，以保证页面的每个区域能够稳健地排布起来。下面简单介绍一下它的工作原理：

* 通过`row`在水平方向建立一组`column`（简写col）
* 你的内容应当放置于`col`内，并且，只有`col`可以作为`row`的直接元素
* 栅格系统中的列是指1到24的值来表示其跨越的范围。例如，三个等宽的列可以使用`.col-8`来创建
* 如果一个`row`中的`col`总和超过 24，那么多余的`col`会作为一个整体另起一行排列

## Flex 布局

我们的栅格化系统支持 Flex 布局，允许子元素在父节点内的水平对齐方式 - 居左、居中、居右、等宽排列、分散排列。子元素与子元素之间，支持顶部对齐、垂直居中对齐、底部对齐的方式。同时，支持使用 order 来定义元素的排列顺序。

Flex 布局是基于 24 栅格来定义每一个『盒子』的宽度，但排版则不拘泥于栅格。

## API

Ant Design 的布局组件若不能满足你的需求，你也可以直接使用社区的优秀布局组件：

- [react-flexbox-grid](http://roylee0704.github.io/react-flexbox-grid/)
- [react-blocks](http://whoisandie.github.io/react-blocks/)

### Row

| 成员        | 说明             | 类型               | 默认值       |
|------------|-----------------|--------------------|-------------|
| gutter     | 栅格间隔   | number | 0        |
| type     | 布局模式，可选 `flex`，现代浏览器下有效 | string |         |
| align     | flex 布局下的垂直对齐方式：`top` `middle` `bottom`  | string | `top`      |
| justify   | flex 布局下的水平排列方式：`start` `end` `center` `space-around` `space-between`   | string | `start`        |

### Col

| 成员        | 说明             | 类型               | 默认值       |
|------------|-----------------|--------------------|-------------|
| span     | 栅格占位格数，为 0 时相当于 `display: none`   | number | 无        |
| order     | 栅格顺序，`flex` 布局模式下有效   | number | 0        |
| offset     | 栅格左侧的间隔格数，间隔内不可以有栅格  | number | 0        |
| push     | 栅格向右移动格数   | number | 0        |
| pull     | 栅格向左移动格数   | number | 0        |

<style>
.markdown .demo-row,
.code-box-demo .demo-row {
    background-image: linear-gradient(90deg, #F5F5F5 4.16666667%, transparent 4.16666667%, transparent 8.33333333%, #F5F5F5 8.33333333%, #F5F5F5 12.5%,  transparent 12.5%, transparent 16.66666667%, #F5F5F5 16.66666667%, #F5F5F5 20.83333333%, transparent 20.83333333%, transparent 25%, #F5F5F5 25%, #F5F5F5 29.16666667%, transparent 29.16666667%, transparent 33.33333333%, #F5F5F5 33.33333333%, #F5F5F5 37.5%, transparent 37.5%, transparent 41.66666667%, #F5F5F5 41.66666667%, #F5F5F5 45.83333333%, transparent 45.83333333%, transparent 50%, #F5F5F5 50%, #F5F5F5 54.16666667%, transparent 54.16666667%, transparent 58.33333333%, #F5F5F5 58.33333333%, #F5F5F5 62.5%, transparent 62.5%, transparent 66.66666667%, #F5F5F5 66.66666667%, #F5F5F5 70.83333333%,  transparent 70.83333333%, transparent 75%, #F5F5F5 75%, #F5F5F5 79.16666667%, transparent 79.16666667%, transparent 83.33333333%, #F5F5F5 83.33333333%, #F5F5F5 87.5%, transparent 87.5%, transparent 91.66666667%, #F5F5F5 91.66666667%, #F5F5F5 95.83333333%, transparent 95.83333333%);
    overflow: hidden;
}
.markdown .row-flex,
.code-box-demo .row-flex {
  background: #F5F5F5;
}

.markdown .row > div,
.code-box-demo .row > div,
.markdown .row-flex > div,
.code-box-demo .row-flex > div {
  padding: 5px 0;
  text-align: center;
  border-radius: 6px;
  min-height: 30px;
  margin-top: 10px;
  margin-bottom: 10px;
  color: #fff;
}

.code-box-demo .row > div:not(.gutter-row) {
  background: #6AC2F5;
  border: 1px solid rgba(0, 0, 0, 0.1);
}

.markdown .row .demo-col,
.code-box-demo .row .demo-col {
  text-align: center;
  padding: 40px 0;
  color: #fff;
  font-size: 18px;
  border: none;
  margin-top: 0;
  margin-bottom: 0;
}
.markdown .row .demo-col-1,
.code-box-demo .row .demo-col-1 {
  background: rgba(29, 128, 211, 0.7);
}
.markdown .row .demo-col-2,
.code-box-demo .row .demo-col-2 {
  background: rgba(29, 128, 211, 0.5);
}
.markdown .row .demo-col-3,
.code-box-demo .row .demo-col-3{
  background: rgba(255, 255, 255, 0.2);
  color: #999;
}
.markdown .row .demo-col-4,
.code-box-demo .row .demo-col-4 {
  background: rgba(29, 128, 211, 0.6);
}
.markdown .row .demo-col-5,
.code-box-demo .row .demo-col-5 {
  background: rgba(255, 255, 255, 0.5);
  color: #999;
}

.markdown .hight-100,
.code-box-demo .hight-100 {
  height: 100px;
}
.markdown .hight-50,
.code-box-demo .hight-50 {
  height: 50px;
}
.markdown .hight-120,
.code-box-demo .hight-120 {
  height: 120px;
}
.markdown .hight-80,
.code-box-demo .hight-80 {
  height: 80px;
}
</style>