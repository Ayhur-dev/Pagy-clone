<template>
  <section class="py-8 md:py-32 px-4 md:px-6 bg-white">
    <div class="max-w-6xl mx-auto">
      <!-- Header -->
      <div ref="headerRef" class="text-center mb-12 md:mb-16 opacity-0">
        <h2
          class="text-3xl md:text-5xl font-semibold tracking-tight text-gray-900 leading-[1.15]"
        >
          What people say
        </h2>
      </div>

      <!-- Masonry-style Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
        <div
          v-for="(tweet, index) in tweets"
          :key="tweet.handle"
          :ref="(el) => (cardRefs[index] = el)"
          class="opacity-0 bg-white rounded-2xl border border-gray-200 p-5 flex flex-col gap-4 hover:shadow-md transition-shadow duration-300"
        >
          <!-- Top row: avatar + name + X icon -->
          <div class="flex items-center justify-between">
            <div class="flex items-center gap-3">
              <!-- Avatar -->
              <div
                class="w-11 h-11 rounded-full overflow-hidden bg-gray-100 shrink-0 border border-gray-200"
              >
                <img
                  v-if="tweet.avatar"
                  :src="tweet.avatar"
                  :alt="tweet.name"
                  class="w-full h-full object-cover"
                />
                <!-- Fallback initials if no image -->
                <div
                  v-else
                  :class="`w-full h-full flex items-center justify-center text-sm font-bold text-white ${tweet.color}`"
                >
                  {{ tweet.initials }}
                </div>
              </div>
              <!-- Name + handle -->
              <div>
                <p class="text-sm font-semibold text-gray-900 leading-tight">
                  {{ tweet.name }}
                </p>
                <p class="text-xs text-gray-400 mt-0.5">{{ tweet.handle }}</p>
              </div>
            </div>

            <!-- X / Twitter logo -->
            <svg
              class="w-5 h-5 text-gray-900 shrink-0"
              viewBox="0 0 24 24"
              fill="currentColor"
            >
              <path
                d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-4.714-6.231-5.401 6.231H2.742l7.73-8.835L1.254 2.25H8.08l4.253 5.622 5.911-5.622Zm-1.161 17.52h1.833L7.084 4.126H5.117z"
              />
            </svg>
          </div>

          <!-- Tweet text -->
          <p class="text-sm text-gray-700 leading-relaxed flex-1">
            {{ tweet.text }}
          </p>

          <!-- Timestamp -->
          <p class="text-xs text-gray-400 mt-auto">{{ tweet.time }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { animate, inView, stagger } from "motion";

const headerRef = ref(null);
const cardRefs = ref([]);

const tweets = [
  {
    name: "Tony Ennis",
    handle: "@tonyennis",
    avatar: "/avatars/tony.avif",
    initials: "TE",
    color: "bg-orange-500",
    text: "Have tried all the landing page builders and @pagyco is still the best for quickly throwing something together. So easy to use, great work @hernansartorio 👋",
    time: "10:44 AM · Mar 8, 2025",
  },
  {
    name: "Nicolas Prieto",
    handle: "@nicopriet0",
    avatar: "/avatars/nicolas.jpg",
    initials: "NP",
    color: "bg-yellow-500",
    text: "I have probably never seen a simpler an funnier way to create a simple website. Kudos to Hernán for the amazing work!",
    time: "9:22 PM · Jul 26, 2025",
  },
  {
    name: "Justin Beausoleil",
    handle: "@jusbeau",
    avatar: "/avatars/justin.avif",
    initials: "JB",
    color: "bg-gray-600",
    text: "Been trying quite a few of these website builders and this might be the fastest, most intuitive, with best results!",
    time: "12:48 AM · May 24, 2023",
  },
  {
    name: "Dak",
    handle: "@dakdevs",
    avatar: "/avatars/dak.jpg",
    initials: "D",
    color: "bg-slate-700",
    text: "Thanks to @hernansartorio's @pagyco I was able to re do my personal site.\n\ndak.dev\n\nI'm generally far too busy building other things that my personal site gets neglected. Pagy made it super easy for me to build an awesome personal site very quickly.",
    time: "",
  },
  {
    name: "Renée",
    handle: "@reneedefour",
    avatar: "/avatars/renee.avif",
    initials: "R",
    color: "bg-rose-500",
    text: "Have I mentioned that I love @pagyco and it's by far the easiest tool to build websites for me? ❤️✨\n\nSo easy, so beautiful, what more could one want?",
    time: "5:58 PM · Aug 11, 2024",
  },
  {
    name: "Roberto Díaz",
    handle: "@_rbart_",
    avatar: "/avatars/roberto.jpg",
    initials: "RD",
    color: "bg-blue-500",
    text: "An example that even a type of product for which there are so many alternatives, by making it better and improving the UX, you can create something amazing that seems like magic.\n\nIt's really cool!",
    time: "10:48 AM · Aug 7, 2024",
  },
  {
    name: "Jeremy",
    handle: "@jeremybasham",
    avatar: "/avatars/jeremy.avif",
    initials: "J",
    color: "bg-slate-700",
    text: "Never had this much fun building a landing page - Definitely worth the upgrade!",
    time: "",
  },
  {
    name: "Nick",
    handle: "@nicksimmard",
    avatar: "/avatars/nick.jpg",
    initials: "N",
    color: "bg-rose-500",
    text: "I was playing with @pagyco yesterday to see if I could use it for a project I’ve got in mind. \n\nMan, it’s downright a joy to use 😊 \n\nStrikes that perfect balance between simplicity and customizability, especially for folks who just want the damn page to be published already!",
    time: "5:58 PM · Aug 11, 2024",
  },
  {
    name: "Steven Tey",
    handle: "@steventey",
    avatar: "/avatars/steven.jpg",
    initials: "ST",
    color: "bg-blue-500",
    text: "An example that even a type of product for which there are so many alternatives, by making it better and improving the UX, you can create something amazing that seems like magic.\n\nIt's really cool!",
    time: "10:48 AM · Aug 7, 2024",
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

  // Stagger cards in as they scroll into view
  const validCards = cardRefs.value.filter(Boolean);
  validCards.forEach((card, i) => {
    inView(
      card,
      () => {
        animate(
          card,
          { opacity: [0, 1], y: [30, 0], scale: [0.96, 1] },
          { duration: 0.5, easing: [0.22, 1, 0.36, 1], delay: (i % 3) * 0.1 },
        );
      },
      { margin: "-60px" },
    );
  });
});
</script>
