<template>
  <div class="comment-reply">
    <!-- 头部信息 -->
    <van-nav-bar :title="`${comment.reply_count}条回复`">
      <van-icon
        slot="left"
        name="cross"
        @click="$emit('close')"
      />
    </van-nav-bar>
    <!-- /头部信息 -->

    <!-- 当前评论项 -->
    <comment-item
      :comment="comment"
    />
    <!-- /当前评论项 -->
  </div>
</template>

<script>
import CommentItem from './comment-item'

export default {
  name: 'CommentReply',
  components: {
    CommentItem
  },
  props: {
    // 查看回复的评论项
    comment: {
      type: Object,
      required: true
    }
  },
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
