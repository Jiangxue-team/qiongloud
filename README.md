# Component library

CSS&JS 组件库(Component library) 基于 JT214-2 提案下的通用框架项目，由 venue.js（审判地）作为最终实现。为之后的所有提案提供通用的组件和样式，保持 Jiangxue TEAM 的设计一致性和视觉效果，通过 Vue 3.0 和 D3 数据可视化框架分别提供视图的渲染和数据可视化的支持。

## gridSystem
### overallArrangement
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

### mainLayout
#### ven-header
横向布局组件通过 ```gap``` 属性实现了栅格数量的划分，并可以通过 DOM attribute 来自适应布局大小。

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