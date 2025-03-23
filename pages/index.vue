<script setup lang="ts">
import {onMounted} from "vue";
import {$fetch} from "ofetch";

interface contentItemI {
  createdAt: String,
  description: String,
  id: String,
  image: String,
  preview: String,
  title: String
}

const content = ref([]);

onMounted(()=>{
  getContent();
})

const getContent = async() => {
  try {
    content.value = await $fetch('https://6082e3545dbd2c001757abf5.mockapi.io/qtim-test-work/posts/');
  } catch (e) {
    console.error(e);
  }
}
</script>

<template>
<header style="padding: 40px; display: flex; align-items: center; justify-content: space-between; margin-bottom: 120px" >
  <img src="/images/qtim-logo.svg" alt="logo">

  <div class="nav-group" style="display: flex; align-items: center">
    <div class="menu" style="margin-right: 90px; font-size: 20px">
      <span style="margin-right: 60px">Works</span>
      <span>About</span>
    </div>
    <div class="buttons" style="display: flex; align-items: center">
      <img src="/images/united-kingdom-ico.svg" alt="lang-ico"
           style="
           margin-right: 16px;
           cursor: pointer;
           padding: 10px;
           /*border: 2px solid #0000001A;*/
           border-radius: 999px;
           "
      />
      <button>Let’s work</button>
    </div>
  </div>
</header>
<main style="padding: 0 112px; margin-bottom: 140px;">
  <h1 style="font-size: 84px; font-weight: 400; margin: 0 0 40px;">Articles</h1>
  <div class="content" style="display: flex; flex-wrap: wrap; row-gap: 40px; column-gap: 20px">
    <div v-for="item in content" :key="item.id" style="width: 20%">
      <img :src="item.image" alt="content_image" style="width: 100%; height: 50%">
      <div>{{ item.description }}</div>
    </div>
  </div>
</main>

<!--  <footer class="footer">-->
<!--    <div class="container">-->
<!--      <p>Follow us on <a href="#">Facebook</a>, <a href="#">Instagram</a>, and <a href="#">Telegram</a>.</p>-->
<!--    </div>-->
<!--  </footer>-->
</template>

<style lang="scss" scoped>
button {
  padding: 16px 32px;
  background-color: #101010;
  color: #fff;
  font-size: 20px;
  font-weight: 400;
  border-radius: 999px;
  cursor: pointer;
  border: none;
}
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f4f4f4;
}
</style>
