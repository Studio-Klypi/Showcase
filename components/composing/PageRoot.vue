<script setup lang="ts">
import type { HTMLAttributes } from "vue";
import { cn } from "~/lib/utils";

interface PageProps {
  name?: string;
  class?: HTMLAttributes["class"];
}
const props = defineProps<PageProps>();
const name = computed((): string => props.name ?? "home");

const { t } = useI18n();
useHead({
  title: t(`${name.value}.tab`),
});
</script>

<template>
  <div
    :data-page="name"
    :class="cn('', props.class)"
  >
    <slot>page {{ name }}</slot>
  </div>
</template>
