<template>
  <NavigationMenuRoot
    v-model="currentTrigger"
    class="relative z-40 flex w-full justify-center"
  >
    <NavigationMenuList class="hidden sm:flex items-center">
      <PrimaryItem v-for="item in menuItems" :key="item.buttonLabel" v-bind="item" />
      <NavigationMenuIndicator
        class="data-[state=hidden]:opacity-0 duration-200 data-[state=visible]:animate-fadeIn data-[state=hidden]:animate-fadeOut top-full z-[1] flex h-[10px] items-end justify-center overflow-hidden transition-[all,transform_250ms_ease]"
      >
        <div
          class="relative top-[70%] h-[10px] w-[10px] rotate-[45deg] rounded-tl-[2px] bg-white shadow-[rgba(0,0,0,0.16)_0px_0px_1px]"
        />
      </NavigationMenuIndicator>
    </NavigationMenuList>

    <div
      class="perspective-[2000px] absolute top-full left-0 flex w-full justify-center"
    >
      <NavigationMenuViewport
        class="data-[state=open]:animate-scaleIn data-[state=closed]:animate-scaleOut relative mt-[10px] h-[var(--radix-navigation-menu-viewport-height)] w-full origin-[top_center] overflow-hidden rounded-xl bg-white transition-[width,_height] duration-300 sm:w-[var(--radix-navigation-menu-viewport-width)] shadow-[rgba(0,0,0,0.16)_0px_1px_4px]"
      />
    </div>
  </NavigationMenuRoot>
</template>

<script setup>
import { ref } from "vue";

const currentTrigger = ref("");

const menuItems = [
  {
    buttonLabel: "Features",
    primaryTitle: "Everything you ever need",
    primaryDescription:
      "We've got everything you need to build a beautiful and sustainable business.",
    primaryLink: "/features",
    secondaryItems: [
      {
        href: "https://stitches.dev/",
        title: "Stitches",
        description: "CSS-in-JS with best-in-class developer experience.",
      },
      {
        href: "/colors",
        title: "Colors",
        description: "Beautiful, thought-out palettes with auto dark mode.",
      },
      {
        href: "https://icons.radix-ui.com/",
        title: "Icons",
        description: "A crisp set of 15x15 icons, balanced and consistent.",
      },
    ],
  },
  {
    buttonLabel: "Pricing",
    primaryTitle: "Simple, predictable pricing",
    primaryLink: "/pricing",
    primaryDescription:
      "We offer competitive pricing and a variety of payment options.",
    secondaryItems: [
      {
        href: "/pricing?plan=personal",
        title: "Personal/Hobby",
        description: "Free for small projects and open source.",
      },
      {
        href: "/pricing?plan=professional",
        title: "Professional",
        description: "For businesses and teams of all sizes.",
      },
      {
        href: "/pricing?plan=enterprise",
        title: "Enterprise",
        description: "For large businesses with custom requirements.",
      },
    ],
  },
  {
    buttonLabel: "Docs",
    primaryTitle: "For developers and designers",
    primaryLink: "/docs",
    primaryDescription:
      "Get started with our comprehensive documentation and guides.",
    secondaryItems: [
      {
        href: "/docs/getting-started",
        title: "Getting Started",
        description: "Start building with our quick start guide.",
      },
      {
        href: "/docs/components",
        title: "Components",
        description: "Explore our extensive component library.",
      },
      {
        href: "/docs/api",
        title: "API Reference",
        description: "Learn about our powerful and flexible API.",
      },
    ],
  },
  {
    buttonLabel: "Blog",
    primaryTitle: "Stories from the community",
    primaryLink: "/blog",
    primaryDescription:
      "Read about the latest news, updates, and stories from the community.",
    secondaryItems: [
      {
        href: "/blog/announcing-neon",
        title: "Announcing Neon",
        description: "The story of how Neon came to be.",
      },
      {
        href: "/blog/why-we-built-neon",
        title: "Why we built Neon",
        description: "The motivation behind building Neon.",
      },
      {
        href: "/blog/our-approach-to-design",
        title: "Our approach to design",
        description: "How we think about design at Neon.",
      },
    ],
  },
];

// shadow-[rgba(100,100,111,0.2)_0px_7px_29px_0px]
</script>
