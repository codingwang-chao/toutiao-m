<template>
  <div class="update-photo">
    <img :src="image">
    <van-nav-bar
      class="toolbar"
      left-text="取消"
      right-text="确认"
      @click-left="$emit('close')"
      @click-right="onConfirm"
    />
  </div>
</template>

<script>
import { updateUserPhoto } from '@/api/user'

export default {
  name: 'UpdatePhoto',
  components: {},
  props: {
    file: {
      // type: Object,
      required: true
    }
  },
  data () {
    return {
      image: window.URL.createObjectURL(this.file)
    }
  },
  computed: {},
  watch: {},
  created () {},
  mounted () {},
  methods: {
    async onConfirm () {
      this.$toast.loading({
        message: '保存中',
        forbidclick: true
      })

      // 如果要求 Content-Type 是 multipart/form-data，则一定要提交 FormData 数据对象，专门用于文件上传的，不能提交 {}，没用
      const fd = new FormData()
      fd.append('photo', this.file)
      await updateUserPhoto(fd)

      // 更新父组件中的用户头像
      this.$emit('update-photo', this.image)

      // 关闭弹出层
      this.$emit('close')

      this.$toast.success('保存成功')
    }
  }
}
</script>

<style scoped lang="less">
.toolbar {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
}
</style>
