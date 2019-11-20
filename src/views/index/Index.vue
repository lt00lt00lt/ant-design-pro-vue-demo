<template>
  <page-view :title="title">
    <a-card>
      <div class="title">Hello World !</div>
      <a-button type="primary" @click="getData()">获取数据</a-button>
    </a-card>
  </page-view>
</template>

<script>
import { PageView } from '@/layouts'
import { axios } from '@/utils/request'

export default {
  name: 'Index',
  components: {
    PageView
  },
  computed: {
    title() {
      return this.$route.meta.title
    }
  },
  methods: {
    getData() {
      axios({
        url: '/seniorFind/duty?pageNum=1&pageSize=3',
        method: 'POST'
      }).then(res => {
        console.log(res)
      })
    }
  }
}
</script>

<style lang="less" scoped>
.title {
  color: rgba(0, 0, 0, 0.85);
  font-size: 16px;
  font-weight: 500;
  margin-bottom: 16px;
}
</style>