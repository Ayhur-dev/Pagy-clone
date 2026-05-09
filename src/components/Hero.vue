<template>
  <section class="pt-42 px-6 text-center">
    <div class="max-w-6xl mx-auto">
      <!-- Headline -->
      <h1
        ref="headlineRef"
        class="lg:text-[3.7rem] md:text-[2.5rem] sm:text-[2rem] text-5xl font-semibold tracking-tight text-gray-900 leading-[1.15] mb-5"
      >
        Build your own website in minutes
      </h1>

      <!-- Subheadline -->
      <p
        ref="subRef"
        class="text-xl font-normal max-w-2xl mx-auto mb-8 leading-relaxed"
      >
        Pick a template, add your content, and publish. No code required.
      </p>

      <!-- CTA -->
      <div ref="ctaRef" class="flex items-center justify-center gap-3 mb-16">
        <a
          href="#"
          class="bg-gray-900 text-white lg:text-lg md:text-md text-sm font-medium px-5 py-4.5 rounded-full hover:bg-gray-700 transition-all duration-200 hover:-translate-y-px"
        >
          Start building for free
        </a>
      </div>

      <!-- Browser Mockup with Video -->
      <div
        ref="previewRef"
        class="rounded-2xl border border-gray-200 shadow-2xl shadow-gray-200/80 overflow-hidden bg-white"
      >
        <!-- Browser Chrome Bar -->
        <div
          class="flex items-center gap-1.5 px-4 py-3 border-b border-gray-100 bg-gray-50"
        >
          <span class="w-2.5 h-2.5 rounded-full bg-red-400"></span>
          <span class="w-2.5 h-2.5 rounded-full bg-yellow-400"></span>
          <span class="w-2.5 h-2.5 rounded-full bg-green-400"></span>
          <div
            class="flex-1 mx-4 bg-white border border-gray-200 rounded-md h-6 flex items-center justify-center"
          >
            <span class="text-[11px] text-gray-400">pagy.co</span>
          </div>
        </div>

        <!-- Video -->
        <div class="relative w-full bg-gray-50" style="aspect-ratio: 16/9">
          <video
            class="w-full h-full object-cover"
            autoplay
            muted
            loop
            playsinline
            src="/demo.mp4"
          >
            Your browser does not support the video tag.
          </video>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { animate } from "motion";

const badgeRef = ref(null);
const headlineRef = ref(null);
const subRef = ref(null);
const ctaRef = ref(null);
const previewRef = ref(null);

onMounted(() => {
  animate(
    badgeRef.value,
    { opacity: [0, 1], y: [10, 0] },
    { duration: 0.5, easing: "ease-out", delay: 0.1 },
  );
  animate(
    headlineRef.value,
    { opacity: [0, 1], y: [20, 0] },
    { duration: 0.6, easing: "ease-out", delay: 0.2 },
  );
  animate(
    subRef.value,
    { opacity: [0, 1], y: [20, 0] },
    { duration: 0.6, easing: "ease-out", delay: 0.3 },
  );
  animate(
    ctaRef.value,
    { opacity: [0, 1], y: [20, 0] },
    { duration: 0.6, easing: "ease-out", delay: 0.4 },
  );
  animate(
    previewRef.value,
    { opacity: [0, 1], y: [40, 0] },
    { duration: 0.8, easing: "ease-out", delay: 0.5 },
  );
});
</script>
