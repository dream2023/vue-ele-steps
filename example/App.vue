<template>
  <div>
    <ele-steps
      :steps="steps"
      :stepsAttrs="stepsAttrs"
      v-model="active"
    />
    <el-button @click="goNext">点我下一步</el-button>
    <el-button @click="goPre">点我上一步</el-button>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      active: 0,
      stepsAttrs: {
        'align-center': true
      },
      steps: [
        {
          title: '步骤1',
          description: '测试',
          icon: 'el-icon-edit'
        },
        {
          title: '步骤2',
          description: '测试2',
          icon: 'el-icon-upload'
        },
        {
          title: '步骤3',
          description: '测试2',
          icon: 'el-icon-picture'
        }
      ]
    }
  },
  methods: {
    goNext () {
      this.active += 1
    },
    goPre () {
      this.active -= 1
    }
  }
}
</script>
