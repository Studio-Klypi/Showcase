<script setup lang="ts">
import type { HTMLAttributes } from "vue";
import { cn } from "~/lib/utils";

interface ExternalLinkProps {
  to: string;
  class?: HTMLAttributes["class"];
}
const props = defineProps<ExternalLinkProps>();
</script>

<template>
  <Button
    variant="discretLink"
    size="discret"
    as-child
    :class="cn('', props.class)"
  >
    <NuxtLink
      :to="props.to"
      target="_blank"
    >
      <slot />
    </NuxtLink>
  </Button>
</template>
