<script setup lang="ts">
import type { HTMLAttributes } from "vue";
import { cn } from "~/lib/utils";

const props = defineProps<{
  class?: HTMLAttributes["class"];
}>();
const { t } = useI18n();
</script>

<template>
  <Button :class="cn('justify-start', props.class)">
    {{ t("navigation.cta") }}
  </Button>
</template>
