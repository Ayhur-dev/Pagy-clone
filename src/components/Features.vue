<template>
  <section id="features" class="py-32 px-6 overflow-hidden">
    <div class="max-w-6xl mx-auto">
      <!-- Section Header -->
      <div
        ref="headerRef"
        class="lg:text-center md:text-center text=start mb-20 opacity-0"
      >
        <h2
          class="lg:text-5xl md:text-3xl text-3xl font-bold tracking-tight text-gray-900 leading-[1.15] mt-3"
        >
          From link-in-bios to to full-blown <br />
          websites, and everything in between
        </h2>
        <p class="text-lg mt-5 max-w-md mx-auto leading-relaxed">
          Personal websites, portfolios, landing pages, company sites — build
          anything with the same ease.
        </p>
      </div>

      <!-- Bento Grid -->
      <div class="flex flex-col gap-4">
        <!-- Row 1: Big card left + 2 stacked right -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
          <!-- Card 1 — big, spans 2 rows visually -->
          <div
            ref="card1"
            class="md:col-span-2 rounded-3xl overflow-hidden relative group cursor-pointer opacity-0 bg-gray-900 min-h-80 md:min-h-105"
          >
            <img
              src="/portfolio.png"
              class="w-full h-full object-cover opacity-70 group-hover:opacity-50 group-hover:scale-105 transition-all duration-700"
              alt="Portfolio"
            />
            <div
              class="absolute inset-0 bg-linear-to-t from-gray-900/90 via-transparent to-transparent"
            ></div>
            <div class="absolute bottom-0 left-0 p-6 md:p-8">
              <span
                class="text-xs text-violet-300 font-medium tracking-widest uppercase mb-2 block"
                >Portfolio</span
              >
              <h3
                class="text-white text-2xl md:text-3xl font-semibold leading-snug"
              >
                Show your work <br />
                beautifully
              </h3>
              <p class="text-gray-400 text-sm mt-2">
                Make a lasting impression
              </p>
            </div>
            <div
              class="absolute top-4 right-4 bg-white/10 backdrop-blur-sm text-white text-xs px-3 py-1.5 rounded-full opacity-0 group-hover:opacity-100 transition-all duration-300 translate-y-2 group-hover:translate-y-0"
            >
              Explore →
            </div>
          </div>

          <!-- Right: 2 stacked cards -->
          <div class="col-span-1 flex flex-col gap-4">
            <!-- Card 2 -->
            <div
              ref="card2"
              class="rounded-3xl overflow-hidden relative group cursor-pointer opacity-0 bg-gray-100 min-h-55 md:flex-1"
            >
              <img
                src="/landing.png"
                class="w-full h-full object-cover group-hover:scale-105 transition-all duration-700"
                alt="Landing page"
              />
              <div
                class="absolute inset-0 bg-linear-to-t from-black/60 to-transparent"
              ></div>
              <div class="absolute bottom-0 left-0 p-5">
                <span
                  class="text-xs text-pink-300 font-medium tracking-widest uppercase block mb-1"
                  >Landing Pages</span
                >
                <h3 class="text-white text-base font-semibold">
                  Convert visitors
                </h3>
              </div>
            </div>

            <!-- Card 3 -->
            <div
              ref="card3"
              class="rounded-3xl overflow-hidden relative group cursor-pointer opacity-0 bg-gray-100 min-h-55 md:flex-1"
            >
              <img
                src="/linkinbio.png"
                class="w-full h-full object-cover group-hover:scale-105 transition-all duration-700"
                alt="Link in bio"
              />
              <div
                class="absolute inset-0 bg-linear-to-t from-black/70 to-transparent"
              ></div>
              <div class="absolute bottom-0 left-0 p-5">
                <span
                  class="text-xs text-cyan-300 font-medium tracking-widest uppercase block mb-1"
                  >Link in bio</span
                >
                <h3 class="text-white text-sm font-semibold">All your links</h3>
              </div>
            </div>
          </div>
        </div>

        <!-- Row 2: 3 equal cards -->
        <div class="grid grid-cols-1 sm:grid-cols-3 gap-4">
          <!-- Card 4 -->
          <div
            ref="card4"
            class="rounded-3xl overflow-hidden relative group cursor-pointer opacity-0 bg-gray-100 min-h-55"
          >
            <img
              src="/company.png"
              class="w-full h-full object-cover group-hover:scale-105 transition-all duration-700"
              alt="Company website"
            />
            <div
              class="absolute inset-0 bg-linear-to-t from-black/70 to-transparent"
            ></div>
            <div class="absolute bottom-0 left-0 p-5">
              <span
                class="text-xs text-emerald-300 font-medium tracking-widest uppercase block mb-1"
                >Company Sites</span
              >
              <h3 class="text-white text-base font-semibold">
                Professional presence
              </h3>
            </div>
          </div>

          <!-- Card 5 -->
          <div
            ref="card5"
            class="rounded-3xl overflow-hidden relative group cursor-pointer opacity-0 bg-gray-100 min-h-55"
          >
            <img
              src="/blog.png"
              class="w-full h-full object-cover group-hover:scale-105 transition-all duration-700"
              alt="Blog"
            />
            <div
              class="absolute inset-0 bg-linear-to-t from-black/70 to-transparent"
            ></div>
            <div class="absolute bottom-0 left-0 p-5">
              <span
                class="text-xs text-amber-300 font-medium tracking-widest uppercase block mb-1"
                >Blogs</span
              >
              <h3 class="text-white text-sm font-semibold">Share your story</h3>
            </div>
          </div>

          <!-- Card 6 mini — event -->
          <div
            ref="card6"
            class="rounded-3xl overflow-hidden relative group cursor-pointer opacity-0 bg-gray-900 min-h-55"
          >
            <img
              src="/store.png"
              class="w-full h-full object-cover opacity-50 group-hover:opacity-30 group-hover:scale-105 transition-all duration-700"
              alt="Store"
            />
            <div
              class="absolute inset-0 bg-linear-to-t from-black/80 to-transparent"
            ></div>
            <div class="absolute bottom-0 left-0 p-5">
              <span
                class="text-xs text-orange-300 font-medium tracking-widest uppercase block mb-1"
                >Digital Stores</span
              >
              <h3 class="text-white text-base font-semibold">
                Sell anything, beautifully
              </h3>
              <p class="text-gray-400 text-xs mt-1">Products & memberships</p>
            </div>
          </div>
        </div>
      </div>

      <!-- Floating stat pills -->
      <div
        ref="statsRef"
        class="flex items-center justify-center gap-6 mt-16 opacity-0 flex-wrap"
      >
        <div
          class="flex items-center gap-2 bg-gray-50 border border-gray-100 px-4 py-2.5 rounded-full"
        >
          <span class="text-lg font-semibold text-gray-900">10k+</span>
          <span class="text-sm text-gray-400">websites built</span>
        </div>
        <div
          class="flex items-center gap-2 bg-gray-50 border border-gray-100 px-4 py-2.5 rounded-full"
        >
          <span class="text-lg font-semibold text-gray-900">∞</span>
          <span class="text-sm text-gray-400">template types</span>
        </div>
        <div
          class="flex items-center gap-2 bg-gray-50 border border-gray-100 px-4 py-2.5 rounded-full"
        >
          <span class="text-lg font-semibold text-gray-900">0</span>
          <span class="text-sm text-gray-400">lines of code</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { animate, inView, stagger } from "motion";

const headerRef = ref(null);
const card1 = ref(null);
const card2 = ref(null);
const card3 = ref(null);
const card4 = ref(null);
const card5 = ref(null);
const card6 = ref(null);
const statsRef = ref(null);

onMounted(() => {
  // Header: fade up + blur
  inView(
    headerRef.value,
    () => {
      animate(
        headerRef.value,
        { opacity: [0, 1], y: [40, 0], filter: ["blur(8px)", "blur(0px)"] },
        { duration: 0.8, easing: "ease-out" },
      );
    },
    { margin: "-100px" },
  );

  // Cards: each flies in from a different direction
  const cardAnimations = [
    { el: card1, from: { x: -60, y: 0, rotate: -3 } },
    { el: card2, from: { x: 0, y: -40, rotate: 2 } },
    { el: card3, from: { x: 60, y: -20, rotate: -2 } },
    { el: card4, from: { x: 0, y: 60, rotate: 1 } },
    { el: card5, from: { x: 40, y: 40, rotate: -1 } },
    { el: card6, from: { x: 0, y: 80, rotate: 0 } },
  ];

  cardAnimations.forEach(({ el, from }, i) => {
    inView(
      el.value,
      () => {
        animate(
          el.value,
          {
            opacity: [0, 1],
            x: [from.x, 0],
            y: [from.y, 0],
            rotate: [from.rotate, 0],
            scale: [0.92, 1],
          },
          {
            duration: 0.7,
            easing: [0.22, 1, 0.36, 1],
            delay: i * 0.1,
          },
        );
      },
      { margin: "-80px" },
    );
  });

  // Stats pills pop in with spring-like stagger
  inView(
    statsRef.value,
    () => {
      animate(
        statsRef.value,
        { opacity: [0, 1], y: [20, 0] },
        { duration: 0.5, easing: "ease-out" },
      );
      const pills = statsRef.value.querySelectorAll(":scope > div");
      animate(
        pills,
        { opacity: [0, 1], scale: [0.8, 1], y: [10, 0] },
        { duration: 0.4, easing: [0.34, 1.56, 0.64, 1], delay: stagger(0.1) },
      );
    },
    { margin: "-50px" },
  );
});
</script>
