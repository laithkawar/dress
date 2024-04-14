<template>
  <div class="bg-white">
    <!-- <div class="px-6 py-2 lg:px-8">
      <div class="text-center">
        <p
          class="mt-2 text-3xl font-bold tracking-tight text-gray-700 sm:text-5xl lg:text-5xl"
        >
          افضل ٣ سيرومات للوجه
        </p>
      </div>
    </div> -->
    <div
      class="max-w-2xl px-4 py-6 mx-auto overflow-hidden sm:px-6 sm:py-8 lg:max-w-7xl lg:px-8"
    >
      <h2 class="sr-only">Products</h2>

      <div
        class="grid grid-cols-1 gap-y-8 sm:grid-cols-2 sm:gap-x-2 sm:gap-y-10 lg:grid-cols-3 lg:gap-x-8"
      >
        <div
          v-for="product in products"
          :key="product.id"
          class="relative flex flex-col bg-white border-gray-200 rounded-lg group"
        >
          <div class="-my-4" />
          <div class="bg-white aspect-square">
            <img
              :src="product.imageSrc"
              :alt="product.imageAlt"
              class="object-cover object-center aspect-square"
            />
          </div>
          <div
            class="absolute inset-0 border-2 rounded-lg pointer-events-none"
            :class="product.bordercolor"
            aria-hidden="true"
          />
          <div class="absolute inset-x-0 top-0 transform translate-y-px">
            <div class="flex justify-center transform -translate-y-1/2">
              <span
                class="z-10 inline-flex px-4 font-bold bg-white text-md"
                :class="product.textcolor"
              >
                {{ product.feature }}
              </span>
            </div>
          </div>
          <div class="flex flex-col flex-1 p-4">
            <div class="-my-8" />
            <h3 class="text-3xl font-semibold tracking-tight text-gray-900">
              <span class="absolute inset-1" />
              {{ product.name }}
            </h3>
            <div class="py-1 pt-6">
              <a
                :href="product.link1"
                class="relative block w-full px-6 py-3 text-lg font-bold text-center text-white border border-transparent rounded-lg shadow-md hover:text-gray-900 bg-emerald-500 hover:bg-emerald-300"
              >
                أحصل عليه من أمازون</a
              >
            </div>
            <div class="py-1">
              <a
                :href="product.link2"
                class="relative block w-full px-6 py-3 text-lg font-bold text-center text-white border border-transparent rounded-lg shadow-md hover:text-gray-900 bg-emerald-500 hover:bg-emerald-300"
              >
                أحصل عليه من أمازون</a
              >
            </div>
            <div class="py-1">
              <a
                :href="product.link3"
                class="relative block w-full px-6 py-3 text-lg font-bold text-center text-white border border-transparent rounded-lg shadow-md hover:text-gray-900 bg-emerald-500 hover:bg-emerald-300"
              >
                أحصل عليه من أمازون</a
              >
            </div>
            <!-- <p class="text-sm text-gray-500">{{ product.description }}</p>
            <div class="flex flex-col justify-end flex-1">
              <p class="text-sm italic text-gray-500">
                {{ product.options }}
              </p>
              <p class="text-base font-medium text-gray-900">
                {{ product.price }}
              </p>
            </div> -->
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
    

<script setup>
const products = [
  {
    id: 1,
    feature: "أشهر منتج",
    bordercolor: "border-cyan-200",
    textcolor: "text-cyan-400",
    name: "لاروش بوزيه - سيروم B5",
    link1: "#",
    link2: "#",
    link3: "#",
    // price: "$32",
    // description:
    //   "Look like a visionary CEO and wear the same black t-shirt every day.",
    // options: "Black",
    imageSrc: "imgs/Article3/LaRochePosay-HyaluB5Serum.webp",
    // imageAlt: "Front of plain black t-shirt.",
  },
  {
    id: 2,
    feature: "أفضل منتج",
    bordercolor: "border-yellow-200",
    textcolor: "text-yellow-400",
    name: "كلارنز - دبل سيرم الوجه",
    link1: "#",
    link2: "#",
    link3: "#",
    // price: "$256",
    // description:
    //   "Get the full lineup of our Basic Tees. Have a fresh shirt all week, and an extra for laundry day.",
    // options: "8 colors",
    imageSrc: "imgs/Article3/Clarins-DoubleSerum.webp",
    // imageAlt:
    //   "Eight shirts arranged on table in black, olive, grey, blue, white, red, mustard, and green.",
  },
  {
    id: 3,
    feature: "افضل سعر",
    bordercolor: "border-purple-200",
    textcolor: "text-purple-400",
    name: "سيتافيل - سيروم للترطيب العميق",
    link1: "#",
    link2: "#",
    link3: "#",
    // price: "$32",
    // description:
    //   "Look like a visionary CEO and wear the same black t-shirt every day.",
    // options: "Black",
    imageSrc: "/imgs/Article3/Cetaphil-DeepHydrationSerum.webp",
    // imageAlt: "Front of plain black t-shirt.",
  },
  // More products...
];
</script>