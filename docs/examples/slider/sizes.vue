<template>
  <el-slider v-model="value" show-input size="large"></el-slider>
  <el-slider v-model="value" show-input></el-slider>
  <el-slider v-model="value" show-input size="small"></el-slider>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const value = ref(0)
</script>

<style scoped>
.el-slider {
  margin-top: 20px;
}

.el-slider:first-child {
  margin-top: 0;
}
</style>
