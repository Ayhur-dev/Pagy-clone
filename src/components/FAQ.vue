<template>
  <section class="py-10 md:py-32 px-4 lg:py-30 md:px-6 bg-white">
    <div class="max-w-2xl mx-auto">
      <!-- Header -->
      <div ref="headerRef" class="mb-10 opacity-0">
        <h2
          class="text-3xl md:text-4xl font-semibold tracking-tight text-gray-900"
        >
          Frequently asked questions
        </h2>
      </div>

      <!-- FAQ Items -->
      <div class="flex flex-col gap-7">
        <div
          v-for="(item, index) in faqs"
          :key="index"
          :ref="(el) => (faqRefs[index] = el)"
          class="opacity-0"
        >
          <p class="text-sm md:text-base font-semibold text-gray-900 mb-1.5">
            {{ item.question }}
          </p>
          <p class="text-sm md:text-base text-gray-500 leading-relaxed">
            {{ item.answer }}
          </p>
        </div>
      </div>
    </div>

    <h1 class="text-gray-400 text-center mt-25">Ayhur-dev</h1>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { animate, inView } from "motion";

const headerRef = ref(null);
const faqRefs = ref([]);

const faqs = [
  {
    question: "How many free websites can I create?",
    answer:
      "As many as you want! On that note, if you choose to upgrade one or more of them, they'll each have their own independent subscription.",
  },
  {
    question: "Is this powered by AI?",
    answer: "Nope.",
  },
  {
    question: "I need help, do you provide support?",
    answer:
      "Yes. When you email or send a message through the live chat widget you'll get a reply from an actual human — no bots involved.",
  },
  {
    question: "Who's behind Pagy?",
    answer:
      "Oh hi, I'm Hernán, the one-man show behind Pagy. I built my first website back in 2005 when I was 14 years old. Pagy is the result of everything I've learned since then, packed into one friendly interface that hides away all the complex stuff so that anyone can build a website in no time.",
  },
  {
    question: "Can I use my own domain?",
    answer:
      "Yes! Even on the free plan you can connect a custom domain to your website. We support all major domain registrars and setup takes just a few minutes.",
  },
  {
    question: "What is Pagy branding?",
    answer:
      'On the free plan, a small "Made with Pagy" badge appears in the bottom corner of your website. You can remove it by upgrading to the Starter plan or higher.',
  },
  {
    question: "What happens if I cancel my subscription?",
    answer:
      "If you cancel, your website will be downgraded to the free plan. Your content stays intact but you will lose access to paid features.",
  },
];

onMounted(() => {
  inView(
    headerRef.value,
    () => {
      animate(
        headerRef.value,
        { opacity: [0, 1], y: [20, 0] },
        { duration: 0.6, easing: "ease-out" },
      );
    },
    { margin: "-80px" },
  );

  faqRefs.value.forEach((el, i) => {
    if (!el) return;
    inView(
      el,
      () => {
        animate(
          el,
          { opacity: [0, 1], y: [15, 0] },
          { duration: 0.4, easing: "ease-out", delay: i * 0.07 },
        );
      },
      { margin: "-40px" },
    );
  });
});
</script>
