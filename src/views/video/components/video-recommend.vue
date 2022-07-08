<template>
  <div class="list">
    <appVideoItemVue v-for="item in list" :key="item.id" :video="item" />
  </div>
</template>

<script setup lang="ts">
import { IVideoItem } from '@/views/video/type'
import { ref } from 'vue'
import axios from 'axios'
import appVideoItemVue from '@/components/app-video-item.vue'

const list = ref<IVideoItem[]>([])
axios({
  method: 'get',
  url: '/recommendList'
}).then(({ data }) => {
  list.value = data.result
  console.log(data.result)
})
</script>

<style lang="less" scoped>
.list {
  display: flex;
  flex-wrap: wrap;
  padding: 0 1vw;
}
</style>
