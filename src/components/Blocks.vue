<template>
  <section class="px-4 md:px-6 bg-white">
    <div class="max-w-5xl mx-auto">
      <!-- Header -->
      <div ref="headerRef" class="mb-12 md:mb-16 opacity-0">
        <h2
          class="text-4xl md:text-4xl font-semibold tracking-tight text-gray-900 leading-[1.2] max-w-2xl"
        >
          Build anything using ready-made blocks
        </h2>
        <p class="text-sm md:text-base mt-4 max-w-lg leading-relaxed">
          Pagy gives you pre-designed building blocks that look great out of the
          box, that you can customize in many ways to build any layout you want.
        </p>
      </div>

      <!-- Grid: 1 col mobile → 2 col tablet → 3 col desktop -->
      <div
        class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-3 items-start"
      >
        <!-- Essentials -->
        <div
          ref="b1"
          class="opacity-0 bg-white rounded-2xl p-5 border border-gray-100 shadow-sm hover:shadow-md transition-shadow duration-300"
        >
          <h3 class="text-2xl font-semibold text-gray-900 mb-1">Essentials</h3>
          <p class="text-xs text-gray-400 mb-4 leading-relaxed">
            All the basic building blocks you need to build a modern website.
          </p>

          <div class="bg-gray-50 p-5 rounded-2xl">
            <h1 class="font-semibold text-xl">This is a card</h1>
            <p class="text-xs text-gray-500 mb-5">
              It contains a heading, a paragraph, and a stack with two buttons.
            </p>
            <div class="flex flex-wrap gap-2">
              <button
                class="bg-gray-900 text-white text-[16px] font-medium px-4 py-1.5 rounded-full"
              >
                Primary
              </button>
              <button
                class="border text-gray-600 text-[16px] font-medium px-4 py-1.5 rounded-full"
              >
                Secondary
              </button>
            </div>
          </div>
        </div>

        <!-- Icons -->
        <div
          ref="b2"
          class="opacity-0 bg-white rounded-2xl p-4 border border-gray-100 shadow-sm hover:shadow-md transition-shadow duration-300"
        >
          <h3 class="text-sm font-semibold text-gray-900 mb-1">Icons</h3>
          <p class="text-[11px] text-gray-400 mb-3 leading-relaxed">
            Huge icon library. Make your pages look more professional
          </p>
          <div class="grid grid-cols-5 gap-2">
            <div
              v-for="(Icon, index) in icons"
              :key="index"
              class="aspect-square bg-gray-50 rounded-xl flex items-center justify-center hover:bg-violet-50 hover:text-violet-500 text-gray-500 hover:scale-110 transition-all duration-200 cursor-pointer"
            >
              <component :is="Icon" :size="16" />
            </div>
          </div>
        </div>

        <!-- Links -->
        <div
          ref="b3"
          class="opacity-0 bg-white rounded-2xl p-4 border border-gray-100 shadow-sm hover:shadow-md transition-shadow duration-300"
        >
          <h3 class="text-sm font-semibold text-gray-900 mb-1">Links</h3>
          <p class="text-[11px] text-gray-400 mb-3 leading-relaxed">
            Add external links and get rich previews embedded automatically.
          </p>

          <!-- Rich Link Preview Card -->
          <div
            class="border border-gray-100 rounded-xl overflow-hidden hover:shadow-sm transition-shadow duration-200 cursor-pointer"
          >
            <!-- Logo/Image area -->
            <div
              class="bg-gray-50 flex items-center justify-center py-6 border-b border-gray-100"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 814 1000"
                class="w-16 h-16 text-gray-400 fill-current"
              >
                <path
                  d="M788.1 340.9c-5.8 4.5-108.2 62.2-108.2 190.5 0 148.4 130.3 200.9 134.2 202.2-.6 3.2-20.7 71.9-68.7 141.9-42.8 61.6-87.5 123.1-155.5 123.1s-85.5-39.5-164-39.5c-76 0-103.7 40.8-165.9 40.8s-105-57.8-155.5-127.4C46 790.7 0 663 0 541.8c0-207.8 135.7-317.9 269-317.9 71 0 130.5 46.4 174.9 46.4 42.8 0 109.7-49 190.8-49 30.5.1 108.2 5.5 164.4 72.6zm-234.5-172.8c31.5-36.3 54.3-86.6 54.3-136.9 0-7.1-.6-14.3-1.9-20.1-51.6 1.9-112.7 35.2-149.4 77.2-28.5 32.4-55.1 83.3-55.1 134.2 0 7.7 1.3 15.5 1.9 18 3.2.6 8.4 1.3 13.6 1.3 46.4.1 101.5-31.2 136.6-73.7z"
                />
              </svg>
            </div>
            <!-- Text content -->
            <div class="p-3">
              <p class="text-[12px] font-semibold text-gray-900 mb-1">Apple</p>
              <p class="text-[10px] text-gray-400 leading-relaxed mb-1.5">
                Discover the innovative world of Apple and shop everything
                iPhone, iPad, Apple Watch,...
              </p>
              <p class="text-[10px] text-gray-300">apple.com</p>
            </div>
          </div>
        </div>
        <!-- Images -->
        <div
          ref="b4"
          class="opacity-0 bg-white rounded-2xl p-5 border border-gray-100 shadow-sm hover:shadow-md transition-shadow duration-300"
        >
          <h3 class="text-sm font-semibold text-gray-900 mb-1">Images</h3>
          <p class="text-[11px] text-gray-400 mb-4 leading-relaxed">
            Upload images in any format and have them automatically optimized
            for fast loading.
          </p>
          <div class="relative h-28">
            <div
              class="absolute left-0 top-2 w-20 h-20 md:w-24 md:h-24 bg-white rounded-xl shadow-md border border-gray-100 overflow-hidden rotate-6"
            >
              <img
                src="https://picsum.photos/seed/img3/200/200"
                class="w-full h-full object-cover"
                alt=""
              />
            </div>
            <div
              class="absolute left-8 md:left-10 top-0 w-20 h-20 md:w-24 md:h-24 bg-white rounded-xl shadow-md border border-gray-100 overflow-hidden rotate-3"
            >
              <img
                src="https://picsum.photos/seed/img4/200/200"
                class="w-full h-full object-cover"
                alt=""
              />
            </div>
            <div
              class="absolute left-16 md:left-20 top-3 w-20 h-20 md:w-24 md:h-24 bg-white rounded-xl shadow-md border border-gray-100 overflow-hidden rotate-2"
            >
              <img
                src="https://picsum.photos/seed/img5/200/200"
                class="w-full h-full object-cover"
                alt=""
              />
            </div>
          </div>
        </div>

        <!-- Forms -->
        <div
          ref="b5"
          class="opacity-0 bg-white rounded-2xl p-5 border border-gray-100 shadow-sm hover:shadow-md transition-shadow duration-300"
        >
          <h3 class="text-sm font-semibold text-gray-900 mb-1">Forms</h3>
          <p class="text-[11px] text-gray-400 mb-4 leading-relaxed">
            Collect information from your visitors in a beautiful way
          </p>
          <div class="space-y-2">
            <input
              type="text"
              placeholder="Name"
              class="w-full text-[11px] border border-gray-200 rounded-xl px-3 py-2.5 outline-none focus:border-violet-400 transition-colors bg-gray-50"
            />
            <textarea
              placeholder="Message"
              rows="2"
              class="w-full text-[11px] border border-gray-200 rounded-xl px-3 py-2.5 outline-none focus:border-violet-400 transition-colors bg-gray-50 resize-none"
            ></textarea>
            <button
              class="w-full bg-gray-900 text-white text-[11px] font-medium py-2.5 rounded-xl hover:bg-gray-700 transition-colors"
            >
              Send
            </button>
          </div>
        </div>

        <!-- Maps -->
        <div
          ref="b6"
          class="opacity-0 bg-white rounded-2xl p-5 border border-gray-100 shadow-sm hover:shadow-md transition-shadow duration-300"
        >
          <h3 class="text-sm font-semibold text-gray-900 mb-1">Maps</h3>
          <p class="text-[11px] text-gray-400 mb-4 leading-relaxed">
            Just paste a Google Maps URL and the map will be embedded
            automatically.
          </p>
          <div class="rounded-xl overflow-hidden h-28 relative">
            <img
              src="https://picsum.photos/seed/map2/400/200"
              class="w-full h-full object-cover"
              alt="Map"
            />
            <div class="absolute inset-0 flex items-center justify-center">
              <div
                class="w-7 h-7 bg-red-500 rounded-full flex items-center justify-center shadow-lg border-2 border-white"
              >
                <div class="w-2 h-2 bg-white rounded-full"></div>
              </div>
            </div>
          </div>
        </div>

        <!-- Videos — spans full width on all sizes -->
        <div
          ref="b7"
          class="opacity-0 col-span-1 sm:col-span-2 lg:col-span-2 bg-white rounded-2xl p-5 border border-gray-100 shadow-sm hover:shadow-md transition-shadow duration-300"
        >
          <h3 class="text-sm font-semibold text-gray-900 mb-1">Videos</h3>
          <p class="text-[11px] text-gray-400 mb-4 leading-relaxed">
            Embed any video from YouTube, Vimeo, or upload your own
          </p>
          <div
            class="rounded-xl overflow-hidden relative h-36 md:h-44 bg-gray-900 group cursor-pointer"
          >
            <img
              src="https://picsum.photos/seed/video2/600/300"
              class="w-full h-full object-cover opacity-70 group-hover:opacity-50 transition-opacity duration-300"
              alt=""
            />
            <div class="absolute inset-0 flex items-center justify-center">
              <div
                class="w-10 h-10 bg-white/90 backdrop-blur-sm rounded-full flex items-center justify-center shadow-lg group-hover:scale-110 transition-transform duration-300"
              >
                <span class="text-gray-900 text-xs ml-0.5">▶</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Tweets -->
        <div
          ref="b8"
          class="opacity-0 col-span-1 bg-white rounded-2xl p-5 border border-gray-100 shadow-sm hover:shadow-md transition-shadow duration-300"
        >
          <h3 class="text-sm font-semibold text-gray-900 mb-1">Tweets</h3>
          <p class="text-[11px] text-gray-400 mb-4 leading-relaxed">
            Embed tweets to add social proof to your pages
          </p>
          <div class="space-y-3">
            <div
              v-for="tweet in tweets"
              :key="tweet.handle"
              class="bg-gray-50 rounded-xl p-3 border border-gray-100"
            >
              <div class="flex items-start justify-between mb-2">
                <div class="flex items-center gap-2">
                  <div
                    :class="`w-7 h-7 ${tweet.color} rounded-full flex items-center justify-center text-white text-[10px] font-bold shrink-0`"
                  >
                    {{ tweet.initials }}
                  </div>
                  <div>
                    <p class="text-[10px] font-semibold text-gray-800">
                      {{ tweet.name }}
                    </p>
                    <p class="text-[9px] text-gray-400">{{ tweet.handle }}</p>
                  </div>
                </div>
                <span class="text-gray-300 text-xs shrink-0">✕</span>
              </div>
              <p class="text-[10px] text-gray-600 leading-relaxed">
                {{ tweet.text }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { animate, inView } from "motion";

import {
  Twitter,
  Instagram,
  Youtube,
  Linkedin,
  Github,
  Mail,
  Phone,
  MapPin,
  Globe,
  Heart,
} from "lucide-vue-next";

const headerRef = ref(null);
const b1 = ref(null),
  b2 = ref(null),
  b3 = ref(null);
const b4 = ref(null),
  b5 = ref(null),
  b6 = ref(null);
const b7 = ref(null),
  b8 = ref(null);

const icons = [
  Twitter,
  Instagram,
  Youtube,
  Linkedin,
  Github,
  Mail,
  Phone,
  MapPin,
  Globe,
  Heart,
];

const links = [
  { icon: "🍎", name: "Apple" },
  { icon: "𝕏", name: "Twitter / X" },
  { icon: "📘", name: "Facebook" },
];

const tweets = [
  {
    name: "Sarah Johnson",
    handle: "@sarahjohnson",
    initials: "SJ",
    color: "bg-violet-500",
    text: "Just built my entire portfolio in 20 minutes with Pagy. This tool is insane 🔥",
  },
  {
    name: "Mark Davis",
    handle: "@markdavis",
    initials: "MD",
    color: "bg-blue-500",
    text: "Pagy is genuinely the best no-code builder I've used. So clean and fast!",
  },
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

  const cols = [
    { cards: [b1, b2, b3], dir: { x: -30, y: 0 } },
    { cards: [b4, b5, b6], dir: { x: 0, y: 40 } },
    { cards: [b7, b8], dir: { x: 30, y: 0 } },
  ];

  cols.forEach(({ cards, dir }) => {
    cards.forEach((card, i) => {
      inView(
        card.value,
        () => {
          animate(
            card.value,
            { opacity: [0, 1], x: [dir.x, 0], y: [dir.y, 0], scale: [0.96, 1] },
            { duration: 0.6, easing: [0.22, 1, 0.36, 1], delay: i * 0.1 },
          );
        },
        { margin: "-60px" },
      );
    });
  });
});
</script>
