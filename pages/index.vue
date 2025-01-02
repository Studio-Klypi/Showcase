<script setup lang="ts">
const { t } = useI18n();
</script>

<template>
  <div>
    <h1>{{ t("helloWorld") }}</h1>
    <Button>{{ t("helloWorld") }}</Button>
  </div>
</template>
