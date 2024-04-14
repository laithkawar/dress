<template>
  <div
    class="container grid-cols-12 px-6 pt-4 mx-auto mb-12 lg:px-8 max-w-7xl sm:grid gap-x-12 md:pt-10"
  >
    <div class="col-span-12 overflow-x-hidden lg:col-span-9">
      <BlogHeader
        :title="data.title"
        :image="data.image"
        :alt="data.alt"
        :updatedAt="data.updatedAt"
        :description="data.description"
      />
      <BlogToc class="lg:hidden" />

      <div
        class="mx-auto prose prose-pre:max-w-xs sm:prose-pre:max-w-full prose-base md:prose-lg prose-h1:no-underline max-w-7xl prose-zinc dark:prose-invert prose-img:rounded-lg"
      >
        <ContentRenderer v-if="data" :value="data">
          <template #empty>
            <p>No content found.</p>
          </template>
        </ContentRenderer>
      </div>
    </div>

    <BlogToc
      :defaultOpen="true"
      class="sticky hidden lg:block lg:col-span-3 lg:justify-self-end top-32 h-96"
    />
  </div>
</template>

<script setup>
import { metaFromNuxtContent } from "~/utils/sn-utils-meta";
const { path } = useRoute();

const { data, error } = await useAsyncData(`blog-post-${path}`, () =>
  queryContent(path).findOne()
);

if (error.value) {
  console.error("TODO 404 redirect. Current path:", path);
  throw createError({
    statusCode: 404,
    statusMessage: "Page Not Found",
    fatal: true,
  });
}

useHead(metaFromNuxtContent(data.value));

// Generate OG Image
// defineOgImageComponent('Test', {
//   headline: 'Greetings 👋',
//   title: data.value.title || '',
//   description: data.value.description || '',
//   link: data.value.ogImage,

// })
</script>
