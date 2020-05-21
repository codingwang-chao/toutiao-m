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
        :src="user.photo"
      />
    </van-cell>
    <van-cell
      title="昵称"
      is-link
      :value="user.name"
      @click="isEditNameShow = true"
    />
    <van-cell
      title="性别"
      is-link
      :value="user.gender === 0 ? '男' : '女'"
    />
    <van-cell
      title="生日"
      is-link
      :value="user.birthday"
    />

    <van-popup
      v-model="isEditNameShow"
      position="bottom"
      :style="{ height: '100%' }"
    >
      <!--
        当你传递给子组件的数据既要使用又要修改，例如这里的 name
        这种情况下我们可以使用 v-model 简写
       -->
      <!-- :name="user.name"
      @update-name="user.name = $event" -->

      <!--
        v-model="user.name"
          默认传递一个名字叫 value 的数据 :value="user.name"
          默认监听 input 事件 @input="user.name = $event"
        v-model 的本质还是父子组件通信，它仅仅是简化了父组件的使用
       -->

      <!--
        v-model 只能使用一次
       -->

      <!--
        如果有多个数据需要保持同步，使用 .sync 修饰符。
        :gender="user.gender"
        @update-gender="user.gender = $event"

        :gender.sync="user.gender"
          :gender="user.gender"
          @update:gender="user.gender = $event"
          @update:属性名称="user.gender = $event"

        我们一般把最常用的数据设计为 v-model 绑定，把不太常用的数据设计为 .sync

        参考文档：https://cn.vuejs.org/v2/guide/components-custom-events.html#sync-%E4%BF%AE%E9%A5%B0%E7%AC%A6
       -->
      <update-name
        v-model="user.name"
        :abc.sync="user.gender"
        :a.sync="user.xxx"
        @close="isEditNameShow = false"
      />
    </van-popup>
  </div>
</template>

<script>
import { getUserProfile } from '@/api/user'
import UpdateName from './components/update-name'

export default {
  name: 'UserProfile',
  components: {
    UpdateName
  },
  props: {},
  data () {
    return {
      user: {}, // 用户数据
      isEditNameShow: false // 编辑昵称的显示状态
    }
  },
  computed: {},
  watch: {},
  created () {
    this.loadUserProfile()
  },
  mounted () {},
  methods: {
    async loadUserProfile () {
      const { data } = await getUserProfile()
      this.user = data.data
    }
  }
}
</script>

<style scoped lang="less">
.van-popup {
  background-color: #f5f7f9;
}
</style>
