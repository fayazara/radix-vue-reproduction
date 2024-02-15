<script setup lang="ts">
import { NavigationMenuLink } from 'radix-vue';

const props = defineProps({
  title: String,
});
</script>

<template>
  <li>
    <NavigationMenuLink as-child>
      <a
        v-bind="$attrs"
        class="
          hover:bg-gray-200
          block
          select-none
          rounded-lg
          p-3
          leading-none
          no-underline
          outline-none
          transition-colors
        "
      >
        <div class="text-gray-800 mb-1 font-medium leading-tight">
          {{ props.title }}
        </div>
        <p class="text-gray-500 my-0 leading-normal text-sm">
          <slot />
        </p>
      </a>
    </NavigationMenuLink>
  </li>
</template>
