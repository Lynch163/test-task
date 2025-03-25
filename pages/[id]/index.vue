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
    <h1 style="margin-top: 0; margin-bottom: 40px; font-size: 84px; font-weight: 400">{{cardData.title}}</h1>
    <img :src="cardData.image" alt="content-image" @error="$event.target.src = '/images/qtim-logo.svg'" style="width: 100%; margin-bottom: 80px">
    <div style="width: 50%">
      <div style="margin-bottom: 32px">About</div>
      <div style="font-size: 36px">{{ cardData.description }}</div>
    </div>
  </template>
</template>