<template>
  <div class="max-w-3xl px-4 mx-auto">
    <header class="mt-8 mb-4 flex justify-between items-end">
      <div>
        <h1 class="text-2xl font-semibold">
          <NuxtLink to="/">Nuxt Blog</NuxtLink>
        </h1>
        <p class="text-gray-500">Simple blog powered by Nuxt Content</p>
      </div>

      <Btn>Contact</Btn>
    </header>

    <NuxtPage />
  </div>
</template>

<style>
body {
  @apply bg-gray-100 text-sm;
}
</style>
