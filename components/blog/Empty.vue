<template>
  <button
    type="button"
    class="relative block w-full p-12 text-center border-2 border-gray-300 border-dashed rounded-lg hover:border-gray-400 focus:outline-none focus:ring-2 focus:ring-rose-500 focus:ring-offset-2"
    @click="$router.push('/articles')"
  >
    <Icon
      name="material-symbols-light:article-outline"
      size="1em"
      class="w-12 h-12 mx-auto text-gray-400"
    />
    <span class="block mt-2 text-sm font-semibold text-gray-900"
      >No posts found. See all articles.</span
    >
  </button>
</template>

<script setup>
</script>