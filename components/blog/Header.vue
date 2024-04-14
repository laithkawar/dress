<template>
  <header>
    <h1
      class="my-4 text-xl font-bold dark:text-zinc-300 md:text-3xl lg:text-4xl"
    >
      {{ title }}
    </h1>

    <p
      v-if="description"
      class="mb-6 sm:text-lg text-zinc-600 dark:text-zinc-400"
    >
      {{ description }}
    </p>

    <BaseImg
      v-if="image"
      :src="image"
      :alt="alt"
      :width="800"
      :height="450"
      :placeholder="[48, 27]"
      densities="x1"
      preload
      class="w-full overflow-hidden shadow-lg rounded-2xl"
      fit="inside"
      format="webp"
    />
    <!-- <NuxtPicture v-if="image" :src="image" :alt="alt || ''" width="600" placeholder densities="x1" format="avif,webp" :imgAttrs="{class:'m-auto rounded-2xl shadow-lg h-32 md:h-72 w-4/6 md:w-4/5 content-center object-cover'}" /> -->

    <div
      class="flex w-full mt-6 mb-12 text-xs border-b border-gray-300 md:text-base dark:border-gray-700"
    >
      <div
        class="gap-8 text-xs text-black md:flex dark:text-zinc-300 sm:text-sm"
      >
        <div class="flex items-center py-2 font-semibold">
          <Icon
            name="material-symbols:calendar-month"
            size="1em"
            class="w-5 h-5 ml-2 text-gray-500 dark:text-gray-300"
          />
          <p>{{ dayjs(updatedAt).format("ddd, DD MMM YYYY") }}</p>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import dayjs from "dayjs";

const props = defineProps({
  title: {
    type: String,
  },
  image: {
    type: String,
  },
  alt: {
    type: String,
  },
  description: {
    type: String,
  },
  updatedAt: {
    type: String,
  },
});

const isSVG = computed(() => props.image?.endsWith(".svg"));
</script>
