<template>
  <div class="search-container">
    <!-- 搜索栏 -->
    <!--
      Tips: 在 van-search 外层增加 form 标签，且 action 不为空，即可在 iOS 输入法中显示搜索按钮
     -->
    <form action="/">
      <van-search
        v-model="searchText"
        placeholder="请输入搜索关键词"
        show-action
        @search="onSearch"
        @cancel="$router.back()"
      />
    </form>
    <!-- /搜索栏 -->

    <!-- 联想建议 -->
    <search-suggestion />
    <!-- /联想建议 -->

    <!-- 历史记录 -->
    <!-- /历史记录 -->

    <!-- 搜索结果 -->
    <!-- /搜索结果 -->
  </div>
</template>

<script>
import SearchSuggestion from './components/search-suggestion'

export default {
  name: 'SearchIndex',
  components: {
    SearchSuggestion
  },
  props: {},
  data () {
    return {
      searchText: '' // 搜索输入框的内容
    }
  },
  computed: {},
  watch: {},
  created () {},
  mounted () {},
  methods: {
    onSearch () {
      console.log('onSearch')
    }
  }
}
</script>

<style scoped lang="less"></style>
