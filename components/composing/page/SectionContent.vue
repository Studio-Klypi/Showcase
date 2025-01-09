<script setup lang="ts">
import type { HTMLAttributes } from "vue";
import { cn } from "~/lib/utils";

interface SectionContentProps {
  class?: HTMLAttributes["class"];
}
const props = defineProps<SectionContentProps>();
</script>

<template>
  <main :class="cn('mx-auto w-[min(100%,1080px)] grid grid-cols-4 sm:grid-cols-6 md:grid-cols-8 lg:grid-cols-10 xl:grid-cols-12 gap-4', props.class)">
    <slot />
  </main>
</template>
