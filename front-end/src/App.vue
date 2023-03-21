<template>
  <el-menu class="el-menu-demo" mode="horizontal" @select="handleSelect">
    <el-menu-item index="1">Processing Center</el-menu-item>
    <el-menu-item index="1">
      <b>Animation List</b>
    </el-menu-item>
    <el-menu-item index="2" style="margin-left: auto;">
      <b>Github</b>
    </el-menu-item>
  </el-menu>
  <div id="main-page" class="main-page">
    <div id="left-container" class="left-container">
      <p>abc</p>
    </div>
    <div id="handler" class="handler"></div>
    <div id="right-container" class="right-container">
      <p>abc</p>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import './assets/main.css'

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


<style scoped>
.el-menu-demo {
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
}
</style>
