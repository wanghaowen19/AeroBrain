<script setup>
import page from '../mds/systemoverview_simplify.mdx';
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
        <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
            <page />
        </el-col>
    </el-row>

  </div>
</template>

<style scoped>
/* 选择摘要内容所在的 el-col 元素并应用两端对齐 */
.el-col {
  text-align: justify;
}
</style>