<template>
  <el-steps
    :active="active"
    class="ele-steps"
    v-bind="stepsAttrs"
  >
    <el-step
      :key="index"
      v-bind="step"
      v-for="(step, index) of computedSteps"
    ></el-step>
  </el-steps>
</template>

<script>
export default {
  name: 'EleSteps',
  model: {
    prop: 'active'
  },
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
  },
  watch: {
    active (value) {
      if (value < 0) {
        return this.$emit('input', 0)
      } else if (value > this.steps.length) {
        return this.$emit('input', this.steps.length)
      }
    }
  },
  computed: {
    computedSteps () {
      const steps = this.steps
      const res = steps.map((item) => {
        // 传递过来的steps可以是字符串数组，也可以是对象数组
        // 这里统一转为对象数组
        if (typeof item === 'string') {
          item = {
            title: item
          }
        }
        return item
      })
      return res
    }
  }
}
</script>

<style>
.ele-steps {
  margin-top: 8px;
  margin-bottom: 12px;
}
</style>
