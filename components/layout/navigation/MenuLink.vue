<script setup lang="ts">
import type { HTMLAttributes } from "vue";

interface MenuLinkProps {
  to?: string;
  class?: HTMLAttributes["class"];
}
const props = defineProps<MenuLinkProps>();
</script>

<template>
  <Button
    variant="ghost"
    class="justify-start"
    as-child
  >
    <NuxtLinkLocale
      :to="props.to ?? '/'"
      active-class="bg-secondary text-secondary-foreground"
    >
      <slot>link</slot>
    </NuxtLinkLocale>
  </Button>
</template>
