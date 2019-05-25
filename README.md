# vue-ele-steps | element-ui steps 组件进一步封装，使其更简单

[![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg)](https://opensource.org/licenses/mit-license.php)
[![npm](https://img.shields.io/npm/v/vue-ele-steps.svg)](https://www.npmjs.com/package/vue-ele-steps)
[![size](https://img.shields.io/bundlephobia/minzip/vue-ele-steps.svg)](https://www.npmjs.com/package/vue-ele-steps)
[![download](https://img.shields.io/npm/dw/vue-ele-steps.svg)](https://npmcharts.com/compare/vue-ele-steps?minimal=true)

## 介绍

vue-ele-steps 对 element-ui 中 steps 组件进一步封装，尽量减少了 html 结构，同时未阉割任何功能

## 示例

[https://codepen.io/dream2023/full/wbjGKX/](https://codepen.io/dream2023/full/wbjGKX/)

## 安装

```bash
npm install vue-ele-steps --save
```

## 使用

```js
// 全局引入
import EleSteps from 'vue-ele-steps'
Vue.component(EleSteps.name, EleSteps)
```

```js
// 局部引入
import EleSteps from 'vue-ele-steps'
export default {
  components: {
    EleSteps
  }
}
```

## 示例

#### steps 属性值

```html
<!-- 支持字符串数组 -->
<ele-steps :steps="['步骤1', '步骤2', '步骤3']" :active="1" />
```

```html
<!-- 支持对象数组 -->
<ele-steps
  :steps="[
    { title: '步骤1', description: '描述文字1..', icon: 'el-icon-edit' },
    { title: '步骤2', description: '描述文字2..', icon: 'el-icon-upload' },
    { title: '步骤3', description: '描述文字3..', icon: 'el-icon-picture' }
  ]"
  :active="1"
/>
```

#### 自定义组件属性

```html
<ele-steps
  :stepsAttrs="{
    'align-center': true
  }"
  :steps="['步骤1', '步骤2', '步骤3']"
  :active="1"
/>
```

## Props 参数

```js
props: {
  // steps的属性
  stepsAttrs: {
    type: Object,
    default () {
      return {
        'finish-status': 'success'
      }
    }
  },
  // 步骤数组
  steps: {
    type: Array,
    required: true
  },
  // 当前步骤
  active: {
    type: Number,
    required: true
  }
}
```

## 参考链接

- [element-ui steps 组件]('https://element.eleme.cn/#/zh-CN/component/steps')
