<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  data() {
    return {
      protocol: 'http',
      url: window.location.host,
      activeIndex: '1'
    };
  },
  methods: {
    handleSelect(key: number) {
      if (key == 1) {
        location.href = this.protocol + "://" + this.url;
      }
      else if (key == 2) {
        window.open("https://github.com/Uahh/RepoChart")
      }
    }
  },
})
</script>

<template>
  <el-row>
    <el-col :span="24">
      <el-menu  class="el-menu-demo" mode="horizontal" @select="handleSelect">
        <el-menu-item index="1">Processing Center</el-menu-item>
        <el-sub-menu index="2">
          <template #title>Workspace</template>
          <el-menu-item index="2-1">item one</el-menu-item>
          <el-menu-item index="2-2">item two</el-menu-item>
          <el-menu-item index="2-3">item three</el-menu-item>
          <el-sub-menu index="2-4">
            <template #title>item four</template>
            <el-menu-item index="2-4-1">item one</el-menu-item>
            <el-menu-item index="2-4-2">item two</el-menu-item>
            <el-menu-item index="2-4-3">item three</el-menu-item>
          </el-sub-menu>
        </el-sub-menu>
        <el-menu-item index="3" disabled>Info</el-menu-item>
        <el-menu-item index="4">Orders</el-menu-item>
      </el-menu>
    </el-col>
  </el-row>
</template>

<style scoped>
.el-menu-demo {
  box-shadow: 0 0 20px rgba(0,0,0,0.2);
}
</style>
