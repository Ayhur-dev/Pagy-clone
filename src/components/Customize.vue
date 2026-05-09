<template>
  <section class="py-8 md:py-32 px-4 md:px-6 bg-gray-50 overflow-hidden">
    <div class="max-w-5xl mx-auto">
      <!-- Header -->
      <div ref="headerRef" class="mb-12 md:mb-16 opacity-0">
        <h2
          class="text-4xl md:text-4xl font-semibold tracking-tight text-gray-900 leading-[1.2] max-w-2xl"
        >
          Make it yours, easily
        </h2>
        <p class="text-sm md:text-base mt-4 max-w-lg leading-relaxed">
          Simple customization options that let you express your brand or
          personality with just a few clicks (instead of paralyzing you with
          endless choices).
        </p>
      </div>

      <!-- Preview Content -->
      <div
        class="h-62.5 md:h-100 lg:h-125 transition-colors duration-500 overflow-hidden"
      >
        <video
          class="w-full h-full object-cover"
          autoplay
          muted
          loop
          playsinline
          src="/customize-demo.mp4"
        >
          Your browser does not support the video tag.
        </video>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { animate, inView } from "motion";

const headerRef = ref(null);
const panelRef = ref(null);
const previewRef = ref(null);

const selectedColor = ref("#7c3aed");
const selectedFont = ref("Sans");
const selectedTheme = ref("Light");

const colors = [
  "#7c3aed",
  "#2563eb",
  "#059669",
  "#dc2626",
  "#d97706",
  "#db2777",
  "#0891b2",
  "#111111",
];

const fonts = [
  { name: "Sans", family: "DM Sans, sans-serif" },
  { name: "Serif", family: "Georgia, serif" },
  { name: "Mono", family: "monospace" },
  { name: "Display", family: "DM Serif Display, serif" },
];

const themes = [
  {
    name: "Light",
    bg: "bg-white",
    dot1: "bg-gray-200",
    dot2: "bg-gray-300",
    labelBg: "bg-gray-50",
    labelText: "text-gray-700",
  },
  {
    name: "Dark",
    bg: "bg-gray-900",
    dot1: "bg-gray-600",
    dot2: "bg-gray-700",
    labelBg: "bg-gray-800",
    labelText: "text-gray-200",
  },
  {
    name: "Warm",
    bg: "bg-amber-50",
    dot1: "bg-amber-200",
    dot2: "bg-amber-300",
    labelBg: "bg-amber-50",
    labelText: "text-amber-700",
  },
];

onMounted(() => {
  inView(
    headerRef.value,
    () => {
      animate(
        headerRef.value,
        { opacity: [0, 1], y: [40, 0], filter: ["blur(8px)", "blur(0px)"] },
        { duration: 0.8, easing: "ease-out" },
      );
    },
    { margin: "-80px" },
  );

  inView(
    panelRef.value,
    () => {
      animate(
        panelRef.value,
        { opacity: [0, 1], x: [-50, 0] },
        { duration: 0.7, easing: [0.22, 1, 0.36, 1] },
      );
    },
    { margin: "-80px" },
  );

  inView(
    previewRef.value,
    () => {
      animate(
        previewRef.value,
        { opacity: [0, 1], x: [50, 0] },
        { duration: 0.7, easing: [0.22, 1, 0.36, 1], delay: 0.1 },
      );
    },
    { margin: "-80px" },
  );
});
</script>
