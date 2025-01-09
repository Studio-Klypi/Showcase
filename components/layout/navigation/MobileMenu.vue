<script setup lang="ts">
import { Menu } from "lucide-vue-next";
import MenuCta from "~/components/layout/navigation/MenuCta.vue";
import MenuContent from "~/components/layout/navigation/MenuContent.vue";

const { t } = useI18n();
</script>

<template>
  <Sheet>
    <SheetTrigger class="md:hidden">
      <Button
        variant="ghost"
        size="icon"
      >
        <Menu />
      </Button>
    </SheetTrigger>
    <SheetContent class="flex flex-col">
      <SheetHeader>
        <SheetTitle>{{ t("navigation.title") }}</SheetTitle>
      </SheetHeader>
      <nav class="flex flex-col">
        <MenuContent />
      </nav>

      <MenuCta />
    </SheetContent>
  </Sheet>
</template>
