<template>
  <van-cell
    class="comment-item"
  >
    <van-image
      slot="icon"
      width="36"
      height="36"
      round
      fit="cover"
      :src="comment.aut_photo"
    />
    <div slot="title">
      <div>{{ comment.aut_name }}</div>
      <div>{{ comment.content }}</div>
      <div>
        <span>{{ comment.pubdate }}</span>
        <van-button
          round
          size="mini"
        >回复</van-button>
      </div>
    </div>
    <div>
      <van-icon name="good-job-o" />
      <span>12</span>
    </div>
  </van-cell>
</template>

<script>
export default {
  name: 'CommentItem',
  components: {},
  props: {
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
