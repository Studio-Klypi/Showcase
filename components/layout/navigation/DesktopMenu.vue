<script setup lang="ts">
import MenuContent from "~/components/layout/navigation/MenuContent.vue";
import MenuCta from "~/components/layout/navigation/MenuCta.vue";
</script>

<template>
  <nav class="hidden md:flex flex-1 gap-1">
    <MenuContent />
  </nav>

  <MenuCta class="hidden md:flex" />
</template>
