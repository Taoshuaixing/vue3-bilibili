<template>
  <div class="video-play">
    <video class="video" controls :src="videoInfo?.videoSrc" :poster="videoInfo?.poster"></video>
  </div>
</template>

<script setup lang="ts">
import { defineProps, PropType } from 'vue'
import { IVideoInfo } from '../type'

defineProps({
  videoInfo: {
    type: Object as PropType<IVideoInfo>,
    require: true
  }
})
</script>

<style lang="less" scoped>
.video-play {
  background-color: #000;
  .video {
    width: 100%;
    min-height: 210px;
  }
}
</style>
