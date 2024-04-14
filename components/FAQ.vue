<template>
  <div>
    <div class="px-6 py-24 mx-auto max-w-7xl sm:py-32 lg:px-8 lg:py-40">
      <div class="mx-auto divide-y divide-gray-900/10">
        <h2
          class="text-2xl font-bold leading-10 tracking-tight text-gray-900 dark:text-zinc-300"
        >
          الأسئلة المكررة
        </h2>
        <dl
          class="mt-10 space-y-6 divide-y dark:text-zinc-300 divide-gray-900/10"
        >
          <Disclosure
            as="div"
            v-for="faq in faqs"
            :key="faq.question"
            class="pt-6"
            v-slot="{ open }"
          >
            <dt>
              <DisclosureButton
                class="flex items-start justify-between w-full text-right text-gray-900 dark:text-zinc-300"
              >
                <span class="text-base font-semibold leading-7">{{
                  faq.question
                }}</span>
                <span class="flex items-center ml-6 h-7">
                  <PlusSmallIcon
                    v-if="!open"
                    class="w-6 h-6"
                    aria-hidden="true"
                  />
                  <MinusSmallIcon v-else class="w-6 h-6" aria-hidden="true" />
                </span>
              </DisclosureButton>
            </dt>
            <DisclosurePanel as="dd" class="pl-12 mt-2">
              <p class="text-base leading-7 text-gray-600 dark:text-zinc-300">
                {{ faq.answer }}
              </p>
            </DisclosurePanel>
          </Disclosure>
        </dl>
      </div>
    </div>
  </div>
</template>
  
  <script setup>
import { Disclosure, DisclosureButton, DisclosurePanel } from "@headlessui/vue";
import { MinusSmallIcon, PlusSmallIcon } from "@heroicons/vue/24/outline";

const faqs = [
  {
    question: "ما هي أفضل المنتجات للبشرة؟",
    answer:
      "أفضل المنتجات للبشرة تعتمد على نوع بشرتك واحتياجاتها الخاصة. يوصى بالمنتجات التي تحتوي على مكونات مغذية مثل حمض الهيالورونيك، فيتامين C، والريتينول. لكن من الضروري اختيار المنتجات المناسبة لنوع بشرتك سواء كانت جافة، دهنية، مختلطة أو حساسة.",
  },
  {
    question: "كيف أعرف المنتجات التي تناسب بشرتي؟",
    answer:
      "لمعرفة المنتجات التي تناسب بشرتك، من المهم أولاً تحديد نوع بشرتك ومشاكلها الخاصة. يمكن استشارة أخصائي العناية بالبشرة أو إجراء اختبارات البشرة لتحديد نوعها. بعد ذلك، اختاري المنتجات التي تستهدف مشاكل بشرتك المحددة وتحتوي على مكونات مفيدة لنوع بشرتك.",
  },
  {
    question: "كيف أعرف أن منتج التجميل حقيقي؟",
    answer:
      "للتأكد من أن منتج التجميل حقيقي، اشترِ من المتاجر المعتمدة أو المواقع الإلكترونية الرسمية. تحقق من العبوة للبحث عن أي أخطاء في الطباعة أو الإملاء، وافحص رمز الدفعة وتاريخ الصلاحية. يمكن أيضًا التحقق من صحة المنتج عن طريق مسح الرمز الشريطي أو الاتصال بخدمة عملاء العلامة التجارية..",
  },
  {
    question: "ما هو الترتيب الصحيح لتطبيق منتجات البشرة؟",
    answer:
      "الترتيب الصحيح لتطبيق منتجات العناية بالبشرة يبدأ بالتنظيف، يليه التونر (إذا كنتِ تستخدمينه)، السيرم، الكريم المرطب، وأخيراً واقي الشمس في الصباح. في المساء، استخدمي منظف ومنتجات العلاج المحددة مثل السيرمات والكريمات الليلية.",
  },
  // More questions...
];
</script>