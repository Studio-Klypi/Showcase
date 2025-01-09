<script setup lang="ts">
import type { HTMLAttributes } from "vue";
import { cn } from "~/lib/utils";

interface LayoutProps {
  name?: string;
  class?: HTMLAttributes["class"];
}
const props = defineProps<LayoutProps>();
const name = computed((): string => props.name ?? "default");
</script>

<template>
  <div
    :data-layout="name"
    :class="cn('', props.class)"
  >
    <slot>layout {{ name }}</slot>
  </div>
</template>
