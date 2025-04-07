<script setup lang="ts">
import {onMounted} from "vue";
import type {ContentItemI} from "@/helpers/types";

const cardData = ref<ContentItemI | null>(null);

onMounted(async () => {
  cardData.value = await $fetch<ContentItemI>(`https://6082e3545dbd2c001757abf5.mockapi.io/qtim-test-work/posts/${useRoute().params.id}`);
});
</script>

<template>
  <template v-if="cardData">
    <h1 class="title">{{cardData.title}}</h1>
    <img class="image" :src="cardData.image" alt="content-image" @error="$event.target.src = '/images/qtim-logo.svg'">
    <div class="description-wrapper">
      <div class="description-title">About</div>
      <div class="description-text">{{ cardData.description }}</div>
    </div>
  </template>
</template>

<style lang="scss" scoped>
.title {
  margin-top: 0;
  margin-bottom: 40px;
  font-size: 84px;
  font-weight: 400;
}
.image {
  width: 100%;
  margin-bottom: 80px;
}
.description-wrapper {
  width: 50%;
  & .description-title {
    margin-bottom: 32px;
  }
  & .description-text {
    font-size: 36px;
  }
}
</style>