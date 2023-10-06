<script lang="ts" setup>
useHead({
  title: "Nuxt Content Blog Demo",
});
</script>

<template>
  <div>
    <!-- Blog List  -->
    <ContentList
      path="/posts"
      fields="title,date,thumbnail"
      :query="{
        draft: false,
        sort: [
          {
            date: -1,
          },
        ],
      }"
      v-slot="{ list }"
    >
      <!-- Blog Card  -->
      <div
        v-for="blog in list"
        :key="blog._path"
        class="blog-card bg-white rounded-2xl overflow-hidden mb-4"
      >
        <div class="h-[300px] relative">
          <img
            v-if="blog.thumbnail"
            :src="blog.thumbnail"
            :alt="blog.title"
            class="absolute w-full h-full object-cover"
          />
        </div>

        <div class="blog-card--meta my-4 ml-4">
          <h3 class="text-2xl font-bold">
            <NuxtLink :to="blog.slug">{{ blog.title }}</NuxtLink>
          </h3>
          <div class="text-sm text-gray-500 mt-px block">{{ blog.date }}</div>
          <div v-if="blog.tags" class="mt-2 text-xs">
            <span v-for="tag in blog.tags" class="p-1 rounded bg-gray-100 mr-2">
              {{ tag }}</span
            >
          </div>
        </div>
      </div>
      <!-- ./ Blog Card  -->
    </ContentList>
    <!-- ./ Blog List  -->
  </div>
</template>

<style></style>
