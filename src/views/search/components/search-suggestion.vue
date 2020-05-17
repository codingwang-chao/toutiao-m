<template>
  <div class="search-suggestion">
    <van-cell
      icon="search"
      :title="str"
      v-for="(str, index) in suggestions"
      :key="index"
    ></van-cell>
  </div>
</template>

<script>
import { getSearchSuggestions } from '@/api/search'

export default {
  name: 'SearchSuggestion',
  components: {},
  props: {
    searchText: {
      type: String,
      required: true
    }
  },
  data () {
    return {
      suggestions: [] // 联想建议数据列表
    }
  },
  computed: {},
  // watch 详细的使用语法参考：https://cn.vuejs.org/v2/api/#watch
  watch: {
    // 属性名：要监视的数据的名称
    // searchText () {
    //   console.log('hello')
    // }

    // 这才是监视的完整写法
    searchText: {
      // 当数据发生变化则会执行 handler 处理函数
      async handler () {
        // 找到数据接口
        // 请求获取数据
        // 模板绑定展示
        const { data } = await getSearchSuggestions(this.searchText)
        this.suggestions = data.data.options
      },
      immediate: true // 该回调将会在侦听开始之后被立即调用
    }
  },
  created () {},
  mounted () {},
  methods: {}
}
</script>

<style scoped lang="less"></style>
