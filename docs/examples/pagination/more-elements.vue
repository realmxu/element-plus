<template>
  <div class="flex items-center mb-4">
    <el-radio-group v-model="small" class="mr-4">
      <el-radio-button :label="false">default</el-radio-button>
      <el-radio-button :label="true">small</el-radio-button>
    </el-radio-group>
    <div>
      background:
      <el-switch v-model="background" class="ml-2"></el-switch>
    </div>
    <div class="ml-4">
      disabled: <el-switch v-model="disabled" class="ml-2"></el-switch>
    </div>
  </div>

  <hr class="my-4" />

  <div class="demo-pagination-block">
    <div class="demonstration">Total item count</div>
    <el-pagination
      v-model:currentPage="currentPage1"
      :page-size="100"
      :small="small"
      :disabled="disabled"
      :background="background"
      layout="total, prev, pager, next"
      :total="1000"
      @size-change="handleSizeChange"
      @current-change="handleCurrentChange"
    >
    </el-pagination>
  </div>
  <div class="demo-pagination-block">
    <div class="demonstration">Change page size</div>
    <el-pagination
      v-model:currentPage="currentPage2"
      :page-sizes="[100, 200, 300, 400]"
      :page-size="100"
      :small="small"
      :disabled="disabled"
      :background="background"
      layout="sizes, prev, pager, next"
      :total="1000"
      @size-change="handleSizeChange"
      @current-change="handleCurrentChange"
    >
    </el-pagination>
  </div>
  <div class="demo-pagination-block">
    <div class="demonstration">Jump to</div>
    <el-pagination
      v-model:currentPage="currentPage3"
      :page-size="100"
      :small="small"
      :disabled="disabled"
      :background="background"
      layout="prev, pager, next, jumper"
      :total="1000"
      @size-change="handleSizeChange"
      @current-change="handleCurrentChange"
    >
    </el-pagination>
  </div>
  <div class="demo-pagination-block">
    <div class="demonstration">All combined</div>
    <el-pagination
      v-model:currentPage="currentPage4"
      :page-sizes="[100, 200, 300, 400]"
      :page-size="100"
      :small="small"
      :disabled="disabled"
      :background="background"
      layout="total, sizes, prev, pager, next, jumper"
      :total="400"
      @size-change="handleSizeChange"
      @current-change="handleCurrentChange"
    >
    </el-pagination>
  </div>
</template>
<script lang="ts" setup>
import { ref } from 'vue'

const currentPage1 = ref(5)
const currentPage2 = ref(5)
const currentPage3 = ref(5)
const currentPage4 = ref(4)
const small = ref(false)
const background = ref(false)
const disabled = ref(false)

const handleSizeChange = (val: number) => {
  console.log(`${val} items per page`)
}
const handleCurrentChange = (val: number) => {
  console.log(`current page: ${val}`)
}
</script>

<style scoped>
.demo-pagination-block + .demo-pagination-block {
  margin-top: 10px;
}
.demo-pagination-block .demonstration {
  margin-bottom: 16px;
}
</style>
