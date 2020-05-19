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

    <!-- 所有评论回复 -->
    <van-cell title="所有回复" />
    <comment-list
      :source="comment.com_id"
      type="c"
    />
    <!-- /所有评论回复 -->
  </div>
</template>

<script>
import CommentItem from './comment-item'
import CommentList from './comment-list'

export default {
  name: 'CommentReply',
  components: {
    CommentItem,
    CommentList
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
