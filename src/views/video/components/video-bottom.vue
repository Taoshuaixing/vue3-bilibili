<template>
  <van-tabs v-model:active="activeName">
    <van-tab title="推荐" name="recommend"><videoRecommendVue /></van-tab>
    <van-tab title="评论" name="comment"><videoCommentVue /></van-tab>
  </van-tabs>
</template>

<script setup lang="ts">
import videoCommentVue from './video-comment.vue'
import videoRecommendVue from './video-recommend.vue'
import { ref } from 'vue'

const activeName = ref('recommend')
</script>
