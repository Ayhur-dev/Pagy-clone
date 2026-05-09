<template>
  <section id="pricing" class="py-9 md:py-32 lg:py-0 px-4 md:px-6 bg-white">
    <div class="max-w-6xl mx-auto">
      <!-- Header -->
      <div ref="headerRef" class="text-center mb-12 md:mb-16 opacity-0">
        <h2
          class="text-4xl md:text-5xl font-semibold tracking-tight text-gray-900 mb-5"
        >
          Simple pricing
        </h2>
        <p
          class="text-gray-500 text-base md:text-lg max-w-xl mx-auto leading-relaxed"
        >
          Starts at <em>Free</em>, including custom domains. Yes, you read that
          right. Now you have no excuse to not put all those unused domains to
          use.
        </p>
      </div>

      <!-- Pricing Grid -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
        <!-- Free -->
        <div
          ref="p1"
          class="opacity-0 rounded-2xl border border-gray-200 p-6 flex flex-col gap-6 hover:shadow-md transition-shadow duration-300"
        >
          <div class="flex items-start justify-between">
            <h3 class="text-2xl font-semibold text-gray-900">Free</h3>
            <div class="text-right">
              <span class="text-lg font-semibold text-gray-900">$0</span>
            </div>
          </div>

          <ul class="flex flex-col gap-3 flex-1">
            <li
              v-for="feature in freePlan"
              :key="feature.text"
              class="flex items-start gap-2.5"
            >
              <svg
                class="w-4 h-4 text-gray-900 mt-0.5 shrink-0"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2.5"
              >
                <path
                  d="M20 6L9 17l-5-5"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
              <span class="text-sm text-gray-600" v-html="feature.text"></span>
            </li>
          </ul>

          <button
            class="w-full bg-gray-900 text-white text-sm font-semibold py-3.5 rounded-full hover:bg-gray-700 transition-colors duration-200"
          >
            Start building
          </button>
        </div>

        <!-- Starter -->
        <div
          ref="p2"
          class="opacity-0 rounded-2xl border border-gray-200 p-6 flex flex-col gap-6 hover:shadow-md transition-shadow duration-300"
        >
          <div class="flex items-start justify-between">
            <h3 class="text-2xl font-semibold text-gray-900">Starter</h3>
            <div class="text-right">
              <span class="text-lg font-semibold text-gray-900">$10</span>
              <span class="text-sm text-gray-400">/month</span>
            </div>
          </div>

          <p class="text-sm text-gray-400 -mt-3">
            Everything in <em>Free</em>, plus:
          </p>

          <ul class="flex flex-col gap-3 flex-1">
            <li
              v-for="feature in starterPlan"
              :key="feature.text"
              class="flex items-start gap-2.5"
            >
              <svg
                class="w-4 h-4 text-gray-900 mt-0.5 shrink-0"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2.5"
              >
                <path
                  d="M20 6L9 17l-5-5"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
              <span class="text-sm text-gray-600" v-html="feature.text"></span>
            </li>
          </ul>

          <button
            class="w-full bg-gray-900 text-white text-sm font-semibold py-3.5 rounded-full hover:bg-gray-700 transition-colors duration-200"
          >
            Start building
          </button>
        </div>

        <!-- Pro -->
        <div
          ref="p3"
          class="opacity-0 rounded-2xl border border-gray-200 p-6 flex flex-col gap-6 hover:shadow-md transition-shadow duration-300"
        >
          <div class="flex items-start justify-between">
            <h3 class="text-2xl font-semibold text-gray-900">Pro</h3>
            <div class="text-right">
              <span class="text-lg font-semibold text-gray-900">$20</span>
              <span class="text-sm text-gray-400">/month</span>
            </div>
          </div>

          <p class="text-sm text-gray-400 -mt-3">
            Everything in <em>Starter</em>, plus:
          </p>

          <ul class="flex flex-col gap-3 flex-1">
            <li
              v-for="feature in proPlan"
              :key="feature.text"
              class="flex items-start gap-2.5"
            >
              <svg
                class="w-4 h-4 text-gray-900 mt-0.5 shrink-0"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2.5"
              >
                <path
                  d="M20 6L9 17l-5-5"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
              <span class="text-sm text-gray-600" v-html="feature.text"></span>
            </li>
          </ul>

          <button
            class="w-full bg-gray-900 text-white text-sm font-semibold py-3.5 rounded-full hover:bg-gray-700 transition-colors duration-200"
          >
            Start building
          </button>
        </div>

        <!-- Business -->
        <div
          ref="p4"
          class="opacity-0 rounded-2xl border border-gray-200 p-6 flex flex-col gap-6 hover:shadow-md transition-shadow duration-300"
        >
          <div class="flex items-start justify-between">
            <h3 class="text-2xl font-semibold text-gray-900">Business</h3>
            <div class="text-right">
              <span class="text-lg font-semibold text-gray-900">$40</span>
              <span class="text-sm text-gray-400">/month</span>
            </div>
          </div>

          <p class="text-sm text-gray-400 -mt-3">
            Everything in <em>Pro</em>, plus:
          </p>

          <ul class="flex flex-col gap-3 flex-1">
            <li
              v-for="feature in businessPlan"
              :key="feature.text"
              class="flex items-start gap-2.5"
            >
              <svg
                class="w-4 h-4 text-gray-900 mt-0.5 shrink-0"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2.5"
              >
                <path
                  d="M20 6L9 17l-5-5"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
              <span class="text-sm text-gray-600" v-html="feature.text"></span>
            </li>
          </ul>

          <button
            class="w-full bg-gray-900 text-white text-sm font-semibold py-3.5 rounded-full hover:bg-gray-700 transition-colors duration-200"
          >
            Start building
          </button>
        </div>
      </div>

      <!-- Bottom note -->
      <div ref="noteRef" class="text-center mt-8 opacity-0">
        <p class="text-sm text-gray-500">
          Plus, get <strong class="text-gray-900">3 months free</strong> with
          yearly billing!
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { animate, inView } from "motion";

const headerRef = ref(null);
const p1 = ref(null),
  p2 = ref(null),
  p3 = ref(null),
  p4 = ref(null);
const noteRef = ref(null);

const freePlan = [
  { text: "<strong>1</strong> page" },
  { text: "<strong>1</strong> contributor" },
  { text: "<strong>Unlimited</strong> bandwidth" },
  { text: "<strong>Connect a custom domain</strong>" },
  { text: "Free <em>.pagy.site</em> domain" },
  { text: "Free SSL certificate" },
  { text: "Small Pagy branding" },
];

const starterPlan = [
  { text: "<strong>10</strong> pages" },
  { text: "<strong>2</strong> contributors" },
  { text: "Forms" },
  { text: "Branding free" },
  { text: "Integrations" },
];

const proPlan = [
  { text: "<strong>100</strong> pages" },
  { text: "<strong>5</strong> contributors" },
  { text: "Custom code" },
];

const businessPlan = [
  { text: "<strong>Unlimited</strong> pages" },
  { text: "<strong>Unlimited</strong> contributors" },
];

onMounted(() => {
  inView(
    headerRef.value,
    () => {
      animate(
        headerRef.value,
        { opacity: [0, 1], y: [30, 0], filter: ["blur(6px)", "blur(0px)"] },
        { duration: 0.7, easing: "ease-out" },
      );
    },
    { margin: "-80px" },
  );

  const cards = [p1, p2, p3, p4];
  cards.forEach((card, i) => {
    inView(
      card.value,
      () => {
        animate(
          card.value,
          { opacity: [0, 1], y: [40, 0], scale: [0.96, 1] },
          { duration: 0.5, easing: [0.22, 1, 0.36, 1], delay: i * 0.1 },
        );
      },
      { margin: "-60px" },
    );
  });

  inView(
    noteRef.value,
    () => {
      animate(
        noteRef.value,
        { opacity: [0, 1], y: [10, 0] },
        { duration: 0.5, easing: "ease-out", delay: 0.4 },
      );
    },
    { margin: "-40px" },
  );
});
</script>
