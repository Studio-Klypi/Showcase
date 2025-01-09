<script setup lang="ts">
import { Paintbrush, CodeXml, Aperture, Rocket } from "lucide-vue-next";
import PageRoot from "~/components/composing/PageRoot.vue";
import SectionRoot from "~/components/composing/page/SectionRoot.vue";
import SectionContent from "~/components/composing/page/SectionContent.vue";
import ServiceCard from "~/components/composed/home/ServiceCard.vue";

const { t } = useI18n();
</script>

<template>
  <PageRoot>
    <SectionRoot>
      <SectionContent class="min-h-dvh items-center">
        <div class="flex flex-col gap-5 col-span-4 md:col-span-5 lg:col-span-6">
          <span class="-mb-5 text-lg md:text-xl italic text-muted-foreground/50">{{ t("home.hero.subtitle") }}</span>
          <h1
            class="text-5xl sm:text-6xl md:text-7xl text-pretty font-barlowCondensed font-black"
            v-html="t('home.hero.title')"
          />
          <p class="leading-relaxed text-muted-foreground">
            {{ t("home.hero.caption") }}
          </p>
          <Button
            variant="outline"
            class="self-start"
          >
            <span>{{ t("home.hero.cta") }}</span>
            <Rocket />
          </Button>
        </div>
      </SectionContent>
    </SectionRoot>
    <SectionRoot
      name="services"
      class="py-24"
    >
      <SectionContent>
        <ServiceCard
          service="webdesign"
          :icon="Paintbrush"
        />
        <ServiceCard
          service="development"
          :icon="CodeXml"
          class="lg:col-span-4"
        />
        <ServiceCard
          service="photography"
          :icon="Aperture"
          class="sm:col-start-2 sm:col-span-4 md:col-start-3"
        />
      </SectionContent>
    </SectionRoot>
    <SectionRoot
      name="work"
      class="py-24"
    >
      <SectionContent class="flex flex-col">
        <h2 class="text-4xl lg:text-5xl font-barlowCondensed font-extrabold text-center">
          {{ t("home.work.title") }}
        </h2>

        <!-- todo: carrousel -->
      </SectionContent>
    </SectionRoot>
    <SectionRoot
      name="testimonial"
      class="py-24"
    >
      <SectionContent>
        <!-- todo: testimonial -->
      </SectionContent>
    </SectionRoot>
    <SectionRoot
      name="cta"
      class="py-24 bg-primary"
    >
      <SectionContent>
        <div class="flex flex-col gap-4 col-span-4 md:col-span-5 lg:col-span-6">
          <h2 class="text-5xl text-pretty font-barlowCondensed font-extrabold">
            {{ t("home.cta.title") }}
          </h2>
          <p>{{ t("home.cta.caption") }}</p>
          <Button
            variant="primaryOutline"
            class="self-start"
          >
            {{ t("home.cta.cta") }}
          </Button>
        </div>
      </SectionContent>
    </SectionRoot>
  </PageRoot>
</template>
