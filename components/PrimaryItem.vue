<template>
  <NavigationMenuItem>
    <NavigationMenuTrigger>
      <UButton :label="buttonLabel" color="gray" variant="ghost" class="px-4" />
    </NavigationMenuTrigger>
    <NavigationMenuContent
      class="
        data-[motion=from-start]:animate-enterFromLeft
        data-[motion=from-end]:animate-enterFromRight
        data-[motion=to-start]:animate-exitToLeft
        data-[motion=to-end]:animate-exitToRight
        absolute
        top-0
        left-0
        w-full
        sm:w-auto
      "
    >
      <ul
        class="
          m-0
          grid
          list-none
          gap-x-2
          p-2
          sm:w-[500px] sm:grid-cols-[0.75fr_1fr]
        "
      >
        <li class="row-span-3 grid">
          <NavigationMenuLink as-child>
            <a
              class="
                from-gray-700
                to-gray-900
                h-full
                w-full
                select-none
                rounded-lg
                bg-gradient-to-b
                p-4
                no-underline
                outline-none
                focus:ring-2 focus:ring-offset-2 focus:ring-gray-900
              "
              :href="primaryLink"
            >
              <div
                class="
                  mt-4
                  mb-4
                  text-2xl
                  font-medium
                  leading-[1.2]
                  text-white
                  font-display
                "
              >
                {{ primaryTitle }}
              </div>
              <p class="text-mauve4 text-sm text-white">
                {{ primaryDescription }}
              </p>
            </a>
          </NavigationMenuLink>
        </li>

        <SecondaryItem
          v-for="item in secondaryItems"
          :key="item.href"
          :href="item.href"
          :title="item.title"
        >
          {{ item.description }}
        </SecondaryItem>
      </ul>
    </NavigationMenuContent>
  </NavigationMenuItem>
</template>

<script setup lang="ts">
const props = defineProps<{
  buttonLabel: string;
  primaryTitle: string;
  primaryLink: string;
  primaryDescription: string;
  secondaryItems: { href: string; title: string; description: string }[];
}>();
</script>
