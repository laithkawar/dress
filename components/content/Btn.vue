
<template>
  <div class="py-2">
    <a
      class="relative block px-6 py-3 text-lg font-bold text-center text-white border border-transparent rounded-lg shadow-md hover:text-gray-900 bg-emerald-500 w-72 hover:bg-emerald-300"
      :href="href"
    >
      {{ label }}
    </a>
  </div>
</template>
 
<script>
export default {
  props: {
    label: {
      type: String,
      default: "Click me",
    },
    href: {
      type: String,
      default: "",
    },
  },
};
</script>
