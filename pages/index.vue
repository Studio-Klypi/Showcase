<script setup lang="ts">
import { Paintbrush, CodeXml, Aperture, Rocket } from "lucide-vue-next";
import PageRoot from "~/components/composing/PageRoot.vue";
import SectionRoot from "~/components/composing/page/SectionRoot.vue";
import SectionContent from "~/components/composing/page/SectionContent.vue";
import ServiceCard from "~/components/composed/home/ServiceCard.vue";
import TestimonialCard from "~/components/composed/home/TestimonialCard.vue";
import RecentWorkCarousel from "~/components/composed/home/RecentWorkCarousel.vue";

const { t } = useI18n();

const testimonials: {
  avatarUri?: string;
  author: {
    name: string;
    job: string;
  };
  content: string;
  note: number;
}[] = [
  {
    avatarUri: "images/sophie-doe.png",
    author: {
      name: "Sophie DOE",
      job: "Vétérinaire",
    },
    content: "Lorem ipsum dolor sit amet consectetur. Orci orci lectus elit sit. Scelerisque habitasse proin condimentum ac praesent morbi non potenti sagittis. Vel dui ut ante ultricies varius tortor ut. Massa mauris vulputate arcu lectus cursus erat.",
    note: 4,
  },
  {
    avatarUri: "images/john-doe.png",
    author: {
      name: "John DOE",
      job: "Directeur Artistique",
    },
    content: "Lorem ipsum dolor sit amet consectetur. Orci orci lectus elit sit. Scelerisque habitasse proin condimentum ac praesent morbi non potenti sagittis. Vel dui ut ante ultricies varius tortor ut. Massa mauris vulputate arcu lectus cursus erat.",
    note: 5,
  },
  {
    avatarUri: "images/jane-doe.png",
    author: {
      name: "Jane DOE",
      job: "Photographe",
    },
    content: "Lorem ipsum dolor sit amet consectetur. Orci orci lectus elit sit. Scelerisque habitasse proin condimentum ac praesent morbi non potenti sagittis. Vel dui ut ante ultricies varius tortor ut. Massa mauris vulputate arcu lectus cursus erat.",
    note: 5,
  },
  {
    avatarUri: "images/sarah-maria.png",
    author: {
      name: "Sarah Maria",
      job: "Osthépathe",
    },
    content: "Lorem ipsum dolor sit amet consectetur. Orci orci lectus elit sit. Scelerisque habitasse proin condimentum ac praesent morbi non potenti sagittis. Vel dui ut ante ultricies varius tortor ut. Massa mauris vulputate arcu lectus cursus erat.",
    note: 4.5,
  },
]; // todo: replace with data.
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
    <Separator class="mx-auto w-[min(calc(100%-4rem),1080px)]" />
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
      <SectionContent class="flex flex-col gap-8">
        <h2 class="text-4xl lg:text-5xl font-barlowCondensed font-extrabold text-center">
          {{ t("home.work.title") }}
        </h2>

        <SectionContent>
          <RecentWorkCarousel />
        </SectionContent>
      </SectionContent>
    </SectionRoot>
    <Separator class="mx-auto w-[min(calc(100%-4rem),1080px)]" />
    <SectionRoot
      name="testimonial"
      class="py-24"
    >
      <SectionContent class="items-center grid-rows-4">
        <TestimonialCard
          v-for="(test, index) in testimonials"
          :key="`testimonial-${index})`"
          :avatar-uri="test.avatarUri"
          :author="test.author"
          :content="test.content"
          :note="test.note"
          :class="{
            'lg:row-start-2 xl:col-span-4': index === 0 || index === 3,
            'lg:col-span-4 lg:col-start-4 xl:col-start-5': index === 1 || index === 2,
            'lg:row-start-1': index === 1,
            'lg:row-start-3': index === 2,
          }"
        />
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
