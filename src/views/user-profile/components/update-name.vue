<template>
  <div class="update-name">
    <!-- 导航栏 -->
    <van-nav-bar
      title="修改昵称"
      left-text="取消"
      right-text="完成"
      @click-left="$emit('close')"
      @click-right="onConfirm"
    />
    <!-- /导航栏 -->

    <div class="name-field-wrap">
      <van-field
        v-model="message"
        rows="2"
        autosize
        type="textarea"
        maxlength="50"
        placeholder="请输入留言"
        show-word-limit
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'UpdateName',
  components: {},
  props: {},
  data () {
    return {
      message: ''
    }
  },
  computed: {},
  watch: {},
  created () {},
  mounted () {},
  methods: {
    onConfirm () {
      console.log('onConfirm')
    }
  }
}
</script>

<style scoped lang="less">
.name-field-wrap {
  padding: 10px;
}
</style>
