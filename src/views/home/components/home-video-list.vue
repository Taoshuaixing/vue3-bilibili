<template>
  <div class="list">
    <AppVideoItem v-for="item in list" :key="item.id" :video="item" />
  </div>
</template>

<script setup lang="ts">
import axios from 'axios'
import AppVideoItem from '@/components/app-video-item.vue'
import { ref } from 'vue'
import { IVideoItem } from '@/views/video/type'

const list = ref<IVideoItem[]>([])
axios({
  method: 'get',
  url: '/videosList'
}).then((res) => {
  console.log('视频列表数据', res.data.result)
  list.value = res.data.result
})
</script>
<style lang="less">
.list {
  display: flex;
  flex-wrap: wrap;
  padding: 0 1vw;
}
</style>
