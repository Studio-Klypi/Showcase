<script setup lang="ts">
import type { HTMLAttributes } from "vue";
import { cn } from "~/lib/utils";

interface SectionProps {
  name?: string;
  class?: HTMLAttributes["class"];
}
const props = defineProps<SectionProps>();
const name = computed((): string => props.name ?? "hero");
</script>

<template>
  <section
    :data-section="name"
    :class="cn('w-full px-8', props.class)"
  >
    <slot>section {{ name }}</slot>
  </section>
</template>
