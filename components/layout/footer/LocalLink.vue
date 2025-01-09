<script setup lang="ts">
import type { HTMLAttributes } from "vue";
import { cn } from "~/lib/utils";

interface LocalLinkProps {
  to: string;
  class?: HTMLAttributes["class"];
}
const props = defineProps<LocalLinkProps>();
</script>

<template>
  <Button
    variant="discretLink"
    size="discret"
    as-child
    :class="cn('', props.class)"
  >
    <NuxtLinkLocale :to="props.to">
      <slot />
    </NuxtLinkLocale>
  </Button>
</template>
