<template>
  <article
    class="my-2 overflow-hidden border shadow-sm group dark:border-gray-800 rounded-2xl text-zinc-700 dark:text-zinc-300"
  >
    <NuxtLink :to="path" class="grid grid-cols-1 gap-1 sm:grid-cols-10">
      <div class="sm:col-span-3">
        <BaseImg
          v-if="image"
          loading="lazy"
          class="h-full w-full object-cover object-center rounded-t-2xl sm:rounded-l-2xl sm:rounded-t-none shadow-lg group-hover:scale-[1.02] transition-all duration-500"
          :width="300"
          :src="image"
          :alt="alt"
          placeholder
        />
      </div>
      <div class="p-5 sm:col-span-7">
        <h2
          class="pb-1 text-xl font-semibold text-black dark:text-zinc-300 group-hover:text-sky-700 dark:group-hover:text-sky-400"
        >
          {{ title }}
        </h2>
        <p class="text-ellipsis line-clamp-2">
          {{ description }}
        </p>
        <div
          class="mt-2 mb-1 text-sm text-black dark:text-zinc-300 md:flex md:space-x-6"
        >
          <div class="flex items-center">
            <Icon
              name="material-symbols:calendar-month"
              size="1em"
              class="w-5 h-5 ml-2 text-gray-500 dark:text-gray-300"
            />
            <p>{{ dayjs(updatedAt).format("DD MMM YYYY") }}</p>
          </div>
        </div>
        <div
          class="flex items-center pt-2 group-hover:underline text-sky-700 dark:text-sky-400"
        >
          <p>اقرأ المقال</p>
          <Icon
            name="material-symbols:arrow-back-rounded"
            size="1em"
            class="mr-2 duration-500 transform group-hover:translate-x-1"
          />
        </div>
      </div>
    </NuxtLink>
  </article>
</template>

<script setup>
import dayjs from "dayjs";

const props = defineProps({
  path: {
    type: String,
  },
  title: {
    type: String,
  },
  updatedAt: {
    type: String,
  },
  description: {
    type: String,
    default: "no-description",
  },
  image: {
    type: String,
  },
  alt: {
    type: String,
  },
  ogImage: {
    type: String,
  },
});
</script>
