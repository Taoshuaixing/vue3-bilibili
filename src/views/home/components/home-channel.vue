<template>
    <van-tabs v-model:active="active">
        <van-tab v-for="item in navList" :key="item.id" :title="item.text"></van-tab>
    </van-tabs>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import axios from 'axios'
interface INavItem {
    id:string
    text:string
}
const active = ref(0)
const navList = ref<INavItem[]>([])
axios({
  url: '/navList',
  method: 'get'
}).then(res => {
  navList.value = res.data.result
  console.log(res.data.result)
})
</script>
