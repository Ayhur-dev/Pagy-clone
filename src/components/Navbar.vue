<template>
  <header
    ref="navRef"
    class="fixed top-0 left-0 right-0 z-60 bg-white/85 backdrop-blur-md border-b border-gray-100"
  >
    <div
      class="max-w-6xl mx-auto h-20 flex items-center justify-between px-4 md:px-6"
    >
      <!-- Logo -->
      <a
        href="/"
        class="flex items-center gap-2 font-semibold text-xl md:text-2xl tracking-tight text-gray-900 shrink-0 relative z-60"
      >
        <img
          src="/logo.png"
          alt="Pagy"
          class="w-7 h-7 md:w-8 md:h-8 object-contain"
        />
        Pagy
      </a>

      <!-- Desktop Nav -->
      <div class="hidden md:flex items-center gap-8">
        <nav class="flex items-center gap-6">
          <a
            href="#features"
            class="text-sm text-gray-500 hover:text-gray-900 transition-colors duration-200"
            >Features</a
          >
          <a
            href="#pricing"
            class="text-sm text-gray-500 hover:text-gray-900 transition-colors duration-200"
            >Pricing</a
          >
          <a
            href="#signin"
            class="text-sm text-gray-500 hover:text-gray-900 transition-colors duration-200"
            >Sign in</a
          >
        </nav>
        <a
          href="#"
          class="bg-gray-900 text-white text-sm font-medium px-5 h-9 rounded-full inline-flex items-center hover:bg-gray-700 transition-all duration-200 hover:-translate-y-px whitespace-nowrap"
        >
          Start building
        </a>
      </div>

      <!-- Mobile Hamburger Button -->
      <button
        @click="toggleMenu"
        class="md:hidden relative z-60 w-10 h-10 flex items-center justify-center rounded-full transition-colors duration-300"
        :class="isOpen ? 'bg-gray-100' : 'hover:bg-gray-50'"
        aria-label="Toggle menu"
      >
        <div class="w-5 h-4 flex flex-col justify-between">
          <span
            class="block h-0.5 origin-center transition-all duration-500 ease-in-out"
            :class="isOpen ? 'bg-gray-800' : 'bg-gray-800'"
            :style="isOpen ? 'transform: translateY(7px) rotate(45deg)' : ''"
          ></span>
          <span
            class="block h-0.5 bg-gray-800 transition-all duration-300 ease-in-out"
            :style="
              isOpen
                ? 'opacity: 0; transform: scaleX(0)'
                : 'opacity: 1; transform: scaleX(1)'
            "
          ></span>
          <span
            class="block h-0.5 origin-center transition-all duration-500 ease-in-out"
            :class="isOpen ? 'bg-gray-800' : 'bg-gray-800'"
            :style="isOpen ? 'transform: translateY(-7px) rotate(-45deg)' : ''"
          ></span>
        </div>
      </button>
    </div>

    <!-- Full Screen Mobile Overlay -->
    <Teleport to="body">
      <div
        ref="overlayRef"
        class="fixed inset-0 z-50 md:hidden pointer-events-none"
        :class="isOpen ? 'pointer-events-auto' : ''"
      >
        <!-- Backdrop -->
        <div
          class="absolute inset-0 bg-white transition-all duration-500 ease-in-out"
          :style="
            isOpen
              ? 'opacity: 1; clip-path: circle(150% at calc(100% - 2.5rem) 2.5rem)'
              : 'opacity: 1; clip-path: circle(0% at calc(100% - 2.5rem) 2.5rem)'
          "
        ></div>

        <!-- Menu Content -->
        <div
          class="relative h-full flex flex-col px-6 pt-28 pb-10 overflow-hidden pointer-events-auto"
        >
          <!-- Nav Links -->
          <nav class="flex flex-col gap-1 flex-1">
            <a
              v-for="(link, index) in navLinks"
              :key="link.label"
              :href="link.href"
              @click.prevent="handleNavClick(link.href)"
              class="group flex items-center justify-between py-4 overflow-hidden"
              :style="`transition-delay: ${isOpen ? index * 80 + 200 : 0}ms`"
            >
              <div class="flex items-center gap-4">
                <span
                  class="text-xs font-mono text-gray-300 transition-all duration-300"
                  :style="
                    isOpen
                      ? 'opacity: 1; transform: translateX(0)'
                      : 'opacity: 0; transform: translateX(-10px)'
                  "
                  :class="`transition-delay-[${index * 80 + 250}ms]`"
                >
                  0{{ index + 1 }}
                </span>
                <span
                  class="text-3xl font-semibold tracking-tight text-gray-900 transition-all duration-500 group-hover:translate-x-2"
                  :style="
                    isOpen
                      ? `opacity: 1; transform: translateY(0); transition-delay: ${index * 80 + 200}ms`
                      : `opacity: 0; transform: translateY(40px); transition-delay: 0ms`
                  "
                >
                  {{ link.label }}
                </span>
              </div>
              <span
                class="text-gray-300 text-xl transition-all duration-500 group-hover:text-gray-900 group-hover:translate-x-1"
                :style="
                  isOpen
                    ? `opacity: 1; transition-delay: ${index * 80 + 300}ms`
                    : 'opacity: 0'
                "
              >
                →
              </span>
            </a>
          </nav>

          <!-- Bottom CTA -->
          <div
            class="mt-8 transition-all duration-500"
            :style="
              isOpen
                ? 'opacity: 1; transform: translateY(0); transition-delay: 500ms'
                : 'opacity: 0; transform: translateY(20px)'
            "
          >
            <a
              href="#"
              @click="closeMenu"
              class="w-full bg-gray-900 text-white text-base font-medium py-4 rounded-2xl flex items-center justify-center gap-2 hover:bg-gray-700 transition-colors duration-200"
            >
              Start building
              <span class="text-lg">→</span>
            </a>

            <!-- Socials -->
            <div
              class="flex items-center justify-center gap-8 mt-6 transition-all duration-500"
              :style="
                isOpen ? 'opacity: 1; transition-delay: 600ms' : 'opacity: 0'
              "
            >
              <a
                href="#"
                class="text-gray-400 hover:text-gray-900 transition-colors duration-200"
              >
                <svg
                  viewBox="0 0 24 24"
                  class="w-5 h-5 fill-current"
                  aria-label="X / Twitter"
                >
                  <path
                    d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-4.714-6.231-5.401 6.231H2.742l7.73-8.835L1.254 2.25H8.08l4.253 5.622 5.911-5.622Zm-1.161 17.52h1.833L7.084 4.126H5.117z"
                  />
                </svg>
              </a>
              <a
                href="#"
                class="text-gray-400 hover:text-gray-900 transition-colors duration-200"
              >
                <Instagram :size="20" />
              </a>
              <a
                href="#"
                class="text-gray-400 hover:text-gray-900 transition-colors duration-200"
              >
                <Linkedin :size="20" />
              </a>
            </div>
          </div>
        </div>
      </div>
    </Teleport>
  </header>
</template>

<script setup>
import { ref, onMounted, watch } from "vue";
import { animate } from "motion";
import { Twitter, Instagram, Linkedin } from "lucide-vue-next";

const navRef = ref(null);
const overlayRef = ref(null);
const isOpen = ref(false);

const navLinks = [
  { label: "Features", href: "#features" },
  { label: "Pricing", href: "#pricing" },
  { label: "Sign in", href: "#signin" },
];

const toggleMenu = () => {
  isOpen.value = !isOpen.value;
};
const closeMenu = () => {
  isOpen.value = false;
};

const handleNavClick = (href) => {
  isOpen.value = false;
  setTimeout(() => {
    const target = document.querySelector(href);
    if (target) {
      target.scrollIntoView({ behavior: "smooth" });
    }
  }, 300); 
};

// Lock body scroll when menu is open
watch(isOpen, (val) => {
  document.body.style.overflow = val ? "hidden" : "";
});

onMounted(() => {
  animate(
    navRef.value,
    { opacity: [0, 1], y: [-16, 0] },
    { duration: 0.6, easing: "ease-out" },
  );
});
</script>
