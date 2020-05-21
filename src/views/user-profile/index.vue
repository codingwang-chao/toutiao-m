<template>
  <div class="user-profile">
    <!-- 导航栏 -->
    <van-nav-bar
      class="app-nav-bar"
      title="个人信息"
      left-arrow
      @click-left="$router.back()"
    />
    <!-- /导航栏 -->
    <van-cell title="头像" is-link center>
      <van-image
        width="30"
        height="30"
        round
        fit="cover"
        src="https://img.yzcdn.cn/vant/cat.jpeg"
      />
    </van-cell>
    <van-cell title="昵称" is-link value="hello"></van-cell>
    <van-cell title="性别" is-link value="男"></van-cell>
    <van-cell title="生日" is-link value="2020-05-20"></van-cell>
  </div>
</template>

<script>
export default {
  name: 'UserProfile',
  components: {},
  props: {},
  data () {
    return {}
  },
  computed: {},
  watch: {},
  created () {},
  mounted () {},
  methods: {}
}
</script>

<style scoped lang="less"></style>
