<template>
  <appHeaderVue />
  <videoPlayVue :videoInfo="videoInfo" />
  <videoInfoVue :videoInfo="videoInfo" />
  <videoBottomVue />
</template>

<script setup lang="ts">
import appHeaderVue from '@/components/app-header.vue'
import axios from 'axios'
import { ref } from 'vue'
import { useRoute } from 'vue-router'
import videoBottomVue from './components/video-bottom.vue'
import videoInfoVue from './components/video-info.vue'
import videoPlayVue from './components/video-play.vue'
import { IVideoInfo } from './type'
const videoInfo = ref<IVideoInfo>({})
const route = useRoute()

axios({
  method: 'get',
  url: '/videoDetail',
  params: { id: route.params.id }
}).then(({ data }) => {
  videoInfo.value = data.result
  console.log('视频详情数据', data.result)
})
</script>

<style lang="less" scoped></style>
