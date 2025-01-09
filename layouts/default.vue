<script setup lang="ts">
import LayoutRoot from "~/components/composing/LayoutRoot.vue";
import DesktopMenu from "~/components/layout/navigation/DesktopMenu.vue";
import MobileMenu from "~/components/layout/navigation/MobileMenu.vue";
import MasterFooter from "~/components/layout/footer/MasterFooter.vue";
import SectionContent from "~/components/composing/page/SectionContent.vue";
</script>

<template>
  <LayoutRoot>
    <header class="fixed px-8 z-50 top-0 left-1/2 -translate-x-1/2 w-full h-20 flex justify-between md:justify-normal md:gap-16 items-center bg-background">
      <SectionContent class="flex justify-between md:justify-normal md:gap-16 items-center bg-background">
        <NuxtLinkLocale
          to="/"
          class="flex flex-col"
        >
          <span class="text-sm leading-none opacity-30">Studio</span>
          <p class="text-xl font-black">
            Klypi
          </p>
        </NuxtLinkLocale>

        <DesktopMenu />
        <MobileMenu />
      </SectionContent>
    </header>

    <slot />

    <MasterFooter />
  </LayoutRoot>
</template>
