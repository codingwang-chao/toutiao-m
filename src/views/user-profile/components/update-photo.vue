<template>
  <div class="update-photo">
    <img :src="image">
  </div>
</template>

<script>
export default {
  name: 'UpdatePhoto',
  components: {},
  props: {
    image: {
      type: String,
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
