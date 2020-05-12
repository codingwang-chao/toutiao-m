<template>
  <div class="home-container">
    <!-- 导航栏 -->
    <van-nav-bar class="app-nav-bar">
      <van-button
        slot="title"
        class="search-btn"
        icon="search"
        type="info"
        round
        size="small"
      >搜索</van-button>
    </van-nav-bar>
    <!-- /导航栏 -->

    <!-- 文章频道列表 -->
    <van-tabs v-model="active">
      <van-tab title="标签 1">内容 1</van-tab>
      <van-tab title="标签 2">内容 2</van-tab>
      <van-tab title="标签 3">内容 3</van-tab>
      <van-tab title="标签 4">内容 4</van-tab>
      <van-tab title="标签 5">内容 5</van-tab>
    </van-tabs>
    <!-- /文章频道列表 -->
  </div>
</template>

<script>
export default {
  name: 'HomeIndex',
  components: {},
  props: {},
  data () {
    return {
      active: 0 // 控制被激活的标签
    }
  },
  computed: {},
  watch: {},
  created () {},
  mounted () {},
  methods: {}
}
</script>

<style scoped lang="less">
.home-container {
  /deep/ .van-nav-bar__title {
    max-width: none;
  }
  .search-btn {
    width: 277px;
    height: 32px;
    background: #5babfb;
    border: none;
    .van-icon {
      font-size: 16px;
    }
    .van-button__text {
      font-size: 14px;
    }
  }
}
</style>
