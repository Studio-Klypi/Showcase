<script setup lang="ts">
import type { HTMLAttributes } from "vue";
import { cn } from "~/lib/utils";

interface ActionLinkProps {
  to: string;
  class?: HTMLAttributes["class"];
}
const props = defineProps<ActionLinkProps>();
</script>

<template>
  <Button
    variant="discretLink"
    size="discret"
    as-child
    :class="cn('', props.class)"
  >
    <NuxtLink :to="props.to">
      <slot />
    </NuxtLink>
  </Button>
</template>
