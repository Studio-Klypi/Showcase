<script setup lang="ts">
import type { HTMLAttributes } from "vue";
import { Card, CardHeader, CardTitle } from "~/components/ui/card";
import { cn } from "~/lib/utils";

interface ServiceCardProps {
  service: string;
  icon: Component;
  class?: HTMLAttributes["class"];
}
const props = defineProps<ServiceCardProps>();
const { t } = useI18n();
</script>

<template>
  <Card :class="cn('select-none cursor-pointer flex flex-col col-span-4 sm:col-span-3 md:col-span-4 lg:col-span-3 xl:col-span-4 origin-bottom transition-all duration-300 ease-in-out hover:scale-105 hover:shadow-2xl', props.class)">
    <CardHeader class="flex-row justify-between items-center">
      <CardTitle>{{ t(`home.services.${props.service}.title`) }}</CardTitle>
      <component :is="props.icon" />
    </CardHeader>
    <CardContent class="flex-1">
      <p class="leading-relaxed text-muted-foreground text-pretty">
        {{ t(`home.services.${props.service}.caption`) }}
      </p>
    </CardContent>
    <CardFooter>
      <Button
        variant="outline"
        class="w-full justify-start"
      >
        {{ t("home.services.cta") }}
      </Button>
    </CardFooter>
  </Card>
</template>

<style scoped>

</style>
