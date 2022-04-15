<p align="center">
  <img src="https://49812933408852955071488026628034-1301075051.cos.ap-nanjing.myqcloud.com/202204151842269.png" width="200">
  <h2 align="center">琼楼</h2>
  <p align="center">
  <img src="https://img.shields.io/github/issues/Jiangxue-team/qiongloud" />
  <img src="https://img.shields.io/github/forks/Jiangxue-team/qiongloud" />
  <img src="https://img.shields.io/github/stars/Jiangxue-team/qiongloud">
</p>
</p>
  <p>CSS&JS 组件库(Component library) 基于 JT214-2 提案下的通用框架项目，由 venue.js（审判地）作为最终实现。为之后的所有提案提供通用的组件和样式，保持 Jiangxue TEAM 的设计一致性和视觉效果，通过 Vue 3.0 和 D3 数据可视化框架分别提供视图的渲染和数据可视化的支持。</p>





## Grid System
### Overall Arrangement
#### ven-per
整体布局提供了 ```<ven-per>``` 组件用于 ```10~100%``` 之间的布局宽度，可通过 ```wide``` 属性进行调整。

> 除此之外还提供了 ```<ven-pers>``` 指令，用于支持自定义布局宽度，同样使用 ```wide``` 属性进行调整。


```js
<template>
  <ven-per wide="8"></ven-per>
  <ven-pers wide="10"></template>
</template>

<script>
import hey from './components/hey.vue'
import VenPer from "./components/gridSystem/overallArrangement/venPer";
import VenPers from "./components/gridSystem/overallArrangement/venPers";

export default {
  name: 'App',
  components: {
    VenPers,
    VenPer,
    hey
  }
}
</script>
```

### Main Layout
#### ven-header
横向布局组件通过 ```gap``` 属性实现了栅格数量的划分，并使用 DOM attribute 来自适应布局大小，默认情况下支持 1920~320 大小的设备显示。

```js
<template>
  <ven-header gap="4">
    <div>1</div>
    <div>2</div>
    <div>4</div>
    <div>5</div>
  </ven-header>
</template>

<script>
import venHeader from './components/gridSystem/mainLayout/venHeader.vue'

export default {
  name: 'App',
  components: {
    venHeader
  }
}
</script>
```

#### ven-main
主要布局组件 ```ven-main``` 可支持主体位置以及组件的图层位置，这通常可以使用 ```site```  来调整该区域属性的位置，目前已经可提供 ```center``` 以及 ```left``` 和 ```right``` 的支持。


```js
<template>
  <ven-main site="left">
    <div>1</div>
  </ven-main>
</template>

<script>
import VenMain from "./components/gridSystem/mainLayout/venMain";

export default {
  name: 'App',
  components: {
    VenMain
  }
}
</script>
```

## Modular Design
### Navigation Component
#### ven-bread
面包屑，通过 ```ven-bread``` 组件进行添加和使用，可通过 ```loaf[true,false]``` method 来决定是否使用面包屑。

他的主要作用是在 Navigation link 过多的时候自动进行折叠，并通过 bread 来进行 show/close。

```js
<template>
    <ven-header gap="2" class="vavigation-con vavigation-link" style="max-width: 100%;">
      <div style="height: 100%;display: flex;">
        <ven-logo img="https://gitee.com/analysis-of-river-snow/drawing-bed/raw/master/20211012105711.png"></ven-logo>
      </div>
      <div>
        <ven-nav>
          <ven-main site="-webkit-right" class="vavigation-link">
            <ven-bread :loaf="true">
              <a href="#">Link1</a>
              <a href="#">Link2</a>
              <a href="#">Link3</a>
              <a href="#">Link4</a>
              <a href="#">Link5</a>
              <a href="#">Link6</a>
              <a href="#">Link7</a>
              <a href="#">Link8</a>
              <a href="#">Link9</a>
            </ven-bread>
          </ven-main>
        </ven-nav>
      </div>
    </ven-header>
</template>
<script>
import VenHeader from "./components/gridSystem/mainLayout/venHeader";
import VenMain from "./components/gridSystem/mainLayout/venMain";
import VenBread from "./components/modularDesign/navigationComponent/venBread";
import VenNav from "./components/modularDesign/navigationComponent/venNav";
import VenLogo from "./components/modularDesign/navigationComponent/venLogo";
export default {
  name: 'App',
  components: {
    VenLogo,
    VenNav,
    VenBread,
    VenMain,
    VenHeader,
  }
}
</script>
```

#### ven-logo
通过 ```img``` 函数让 ```ven-logo``` 组件添加 Logo，并自动进行适配。

#### ven-nav
将 ```ven-bread``` 进行包裹形成框架，使得其可通过 ```ven-nav``` 来进行适配

### Navigation Link
#### ven-son
```ven-son``` 组件通过 ```title``` method 以及 ```son``` method 分别实现父导航和子导航的绑定，假设 ```title``` 为 ```fat``` ：

```
<ven-son title="fat" son="son">
	// link ……
</ven-son>
```

则 ``` // link``` 处将会绑定 ```son```  method parameter ，而 ```title``` 内的 parameter 则绑定为 ```fat``` 作为父导航，```son``` 为子导航，你可以配合Navigation Component 组件进行使用。

```js
<template>
  <ven-header gap="2" class="vavigation-con vavigation-link" style="max-width: 100%;">
      <ven-logo img="https://gitee.com/analysis-of-river-snow/drawing-bed/raw/master/20211012105711.png"></ven-logo>
      <ven-nav>
        <ven-main site="-webkit-right" class="vavigation-link">
          <ven-bread :loaf="true">
            <a href="#">Introduction</a>
            <a href="#">Business</a>
            <ven-son title="Staff" son="1">
              <a href="">Link sonOne</a>
              <a href="">Link sonOno</a>
              <a href="">Link sonOne</a>
            </ven-son>
            <ven-son title="Corporate Responsibility" son="2">
              <a href="">Link sonTwo</a>
              <a href="">Link sonTwo</a>
              <a href="">Link sonTwo</a>
            </ven-son>
            <a href="#">Investor</a>
            <a href="#">Media</a>
          </ven-bread>
        </ven-main>
      </ven-nav>
  </ven-header>
</template>
<script>
import VenHeader from "./components/gridSystem/mainLayout/venHeader";
import VenMain from "./components/gridSystem/mainLayout/venMain";
import VenBread from "./components/modularDesign/navigationComponent/venBread";
import VenNav from "./components/modularDesign/navigationComponent/venNav";
import VenLogo from "./components/modularDesign/navigationComponent/venLogo";
import VenSon from "./components/modularDesign/navigationComponent/navigationLink/venSon";
export default {
  name: 'App',
  components: {
    VenLogo,
    VenNav,
    VenBread,
    VenMain,
    VenHeader,
    VenSon
  }
}
</script>
```

## Basic Components
### ven-color
我们提供了多种颜色可以进行搭配，这主要通过 ```col```  methood 或 ```spa``` method 来进行选择颜色或过滤度，之后 通过  ```back``` method 来选择是否应用与颜色或背景中。

1. red
2. blue
3. green
4. blue-green
4. white
5. black
6. yellow

```js
<template>
    <h1><ven-color col="blue" spa="1" :back="true">Hello,world</ven-color></h1>
</template>
<script>
import VenColor from "./components/basicComponents/venColor";
export default {
  name: 'App',
  components: {
    VenColor
  }
}
</script>
```

### ven-font
字体间的大小和行高都会给用户带来最直观的视觉显示，通过 ```size``` 以及 ```row``` method 可以快速调节文字的行高以及大小等，使得更符合规范。

```js
<template>
  <div style="margin: 5%">
    <ven-font size="h1" row="0.1">Component library H1</ven-font>
    <ven-font>CSS&JS component library (Component library) is based on the general framework project under the JT214-2 proposal, and is finally implemented by venue.js (trial site). Provide common components and styles for all subsequent proposals, maintain the design consistency and visual effects of Jiangxue TEAM, and provide support for view rendering and data visualization through Vue 3.0 and D3 data visualization frameworks.</ven-font>
  </div>
</template>
<script>
import VenFont from "./components/basicComponents/ven-font";
export default {
  name: 'App',
  components: {
    VenFont,
  }
}
</script>
```

### ven-button
```ven-button``` 组件支持 ```ven-color``` method 即 ```col``` 和 ```spa``` 还有 ```:back``` 以及在此基础上所添加的 ```font``` method ，用于选择文字的颜色。同时还有 ```ico``` method ，用于添加按钮 icon ，可直接在该 method 参数中填写 icon 的 url。

```js
<template>
  <div style="margin: 5%">
    <ven-font size="h1" row="0.1">Component library ven-button</ven-font>
    <ven-button spa="1" col="blue" :back="false" font="white" ico="https://gitee.com/analysis-of-river-snow/drawing-bed/raw/master/20211019085429.png" class="basic-padding">Update1</ven-button>
    <ven-button spa="8" col="blue" :back="false" font="white" class="basic-padding">Update3</ven-button>
    <ven-button spa="1" :back="false" font="blue" class="basic-padding" ico="https://gitee.com/analysis-of-river-snow/drawing-bed/raw/master/20211019081306.png">Update4</ven-button>
    <ven-button spa="4" :back="false" font="red" class="basic-padding">Update5</ven-button>

    <ven-font size="h1" row="0.1">Icon</ven-font>
    <ven-button spa="9" :back="false" font="white" class="basic-padding" style="padding: 0" ico="https://gitee.com/analysis-of-river-snow/drawing-bed/raw/master/20211019081306.png"></ven-button>
  </div>
</template>
<script>
import VenFont from "./components/basicComponents/venFont";
import VenButton from "./components/basicComponents/venButton";
export default {
  name: 'App',
  components: {
    VenButton,
    VenFont,
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
.basic-padding {
  margin-right: 1em;
}
</style>
```

### ven-link
为链接所提供的组件，有三种不同种类的正式场合样式，分别为 ```nor``` 和 ```ico``` 以及 ```hoz```，可通过 ```to``` method 来指定跳转 uri。

```js
<template>
  <div style="margin: 5%;">
    <ven-link to="https://baidu.com/" type="nor" style="padding: 1em">http://www.baidu.com</ven-link>
    <ven-link to="https://baidu.com/" type="ico" style="padding: 1em">http://www.baidu.com</ven-link>
    <ven-link to="https://baidu.com/" type="hoz" style="padding: 1em">http://www.baidu.com</ven-link>
  </div>
</template>
<script>
import VenLink from "./components/basicComponents/venLink";
export default {
  name: 'App',
  components: {
    VenLink
  }
}
</script>
```
