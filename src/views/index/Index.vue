<template>
  <page-view :title="title">
    <div class="title">Hello World !</div>
    <button @click="getData()">获取数据</button>
  </page-view>
</template>

<script>
import { PageView } from '@/layouts'
import axios from 'axios'

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
      axios.post('/api/seniorFind/duty?pageNum=1&pageSize=3', {}).then(res=>{
          console.log(res);
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