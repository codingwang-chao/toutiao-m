<template>
  <!-- <div class="article-item">文章列表项</div> -->
  <van-cell class="article-item">
    <div slot="title" class="title van-multi-ellipsis--l3">这是标题内容这是标题内容这是标题内容这是标题内容这是标题内容这是标题内容这是标题内容这是标题内容这是标题内容这是标题内容</div>
    <div slot="label">
      <div
        v-if="article.cover.type === 3"
        class="cover-wrap"
      >
        <div class="cover-wrap-item">
          <van-image
            width="116"
            height="73"
            fit="cover"
            v-for="(img, index) in article.cover.images"
            :key="index"
            :src="img"
          />
        </div>
      </div>
      <div class="label-wrap">
        <span>{{ article.aut_name }}</span>
        <span>{{ article.comm_count }}评论</span>
        <span>{{ article.pubdate }}</span>
      </div>
    </div>
    <!-- 默认插槽的名字叫 default，可以省略 -->
    <van-image
      v-if="article.cover.type === 1"
      class="right-cover"
      fit="cover"
      :src="article.cover.images[0]"
    />
  </van-cell>
</template>

<script>
export default {
  name: 'ArticleItem',
  components: {},
  props: {
    article: {
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

<style scoped lang="less">
.article-item {
  .title {
    font-size: 16px;
    color: #3a3a3a;
  }
  /deep/ .van-cell__value {
    flex: unset;
    width: 116px;
    height: 73px;
    margin-left: 12px;
  }
  .right-cover {
    width: 116px;
    height: 73px;
  }
}
</style>
