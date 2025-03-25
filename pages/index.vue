<script setup lang="ts">
import { ref, computed, onMounted } from "vue";
import { $fetch } from "ofetch";
import type {ContentItemI} from "@/helpers/types";

const content = ref<ContentItemI[]>([]);
const currentPage = ref(1);
const itemsPerPage = 8;
const maxPagesToShow = 5;
const startPage = ref(1); // Начальная страница в диапазоне отображаемых страниц
const router = useRouter();

onMounted(() => {
  getContent();
});

const getContent = async () => {
  try {
    content.value = await $fetch('https://6082e3545dbd2c001757abf5.mockapi.io/qtim-test-work/posts/');
  } catch (e) {
    console.error(e);
  }
};

const goToPage = (page: number) => {
  if (page >= 1 && page <= totalPages.value) {
    currentPage.value = page;
  }
};

const nextPages = () => {
  const nextStartPage = startPage.value + maxPagesToShow;
  if (nextStartPage <= totalPages.value) {
    startPage.value = nextStartPage;
  }
};

const prevPages = () => {
  const prevStartPage = startPage.value - maxPagesToShow;
  if (prevStartPage >= 1) {
    startPage.value = prevStartPage;
  }
};

const totalPages = computed(() => Math.ceil(content.value.length / itemsPerPage));

const paginatedContent = computed(() => {
  const start = (currentPage.value - 1) * itemsPerPage;
  const end = start + itemsPerPage;
  return content.value.slice(start, end);
});

const visiblePages = computed(() => {
  const pages = [];
  const endPage = Math.min(startPage.value + maxPagesToShow - 1, totalPages.value);
  for (let i = startPage.value; i <= endPage; i++) {
    pages.push(i);
  }
  return pages;
});
</script>

<template>
    <h1 style="font-size: 84px; font-weight: 400; margin: 0 0 40px">Articles</h1>
    <div class="content" style="display: flex; flex-wrap: wrap; row-gap: 40px; column-gap: 20px; margin-bottom: 50px">
      <div v-for="item in paginatedContent" :key="item.id" style="width: 20%; cursor: pointer" @click="router.push(item.id)">
        <img :src="item.image" @error="$event.target.src = '/images/qtim-logo.svg'" alt="content_image" style="width: 100%; height: 50%; min-height: 135px">
        <div>{{ item.description }}</div>
      </div>
    </div>
    <div class="pagination">
      <button v-if="startPage > 1" @click="prevPages" style="padding: 16px; border: 1px solid gray; border-radius: 12px; cursor: pointer; margin-right: 8px">‹</button>
      <button
          v-for="page in visiblePages"
          :key="page"
          @click="goToPage(page)"
          :style="{
            fontWeight: currentPage === page ? 'bold' : 'normal',
            'background-color': currentPage === page ? '#101010' : '#F3F3F3',
            color: currentPage === page ? '#FFFFFF' : '#000000',
            padding: '16px',
            border: 'none',
            'margin-right': '8px',
            'border-radius': '12px',
            cursor: 'pointer'
           }"
      >
        {{ page }}
      </button>
      <button v-if="startPage + maxPagesToShow <= totalPages" @click="nextPages" style="padding: 16px; border: 1px solid gray; border-radius: 12px; cursor: pointer">›</button>
    </div>
</template>

<style lang="scss" scoped>
</style>