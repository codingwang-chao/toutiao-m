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
        v-model="localName"
        rows="2"
        autosize
        type="textarea"
        maxlength="7"
        placeholder="请输入昵称"
        show-word-limit
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'UpdateName',
  components: {},
  props: {
    name: {
      type: String,
      required: true
    }
  },
  data () {
    return {
      // var a = 1
      // var b = a
      // b = 123
      // a? 1
      localName: this.name
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
