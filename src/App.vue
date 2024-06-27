<template>
  <div id="app">
    <!-- <BackgroundComponent backgroundType="image" backgroundSource="/imgs/bgs/5.png"/> -->
    <BackgroundComponent backgroundType="webpage" backgroundSource="imgs\bgs\html\github\index.html" />

    <IntroductionPage />
  </div>
</template>

<script setup>

import IntroductionPage from './components/IntroductionPage.vue';
import BackgroundComponent from './components/BackgroundComponent.vue';
</script>

<style>
/* 可以根据需要添加全局样式 */
body {
  background-color: #7baff2;
  color: white;
  margin: 0;
  padding: 0;
}
.fp-watermark{
  opacity: 0 !important;
}
</style>
