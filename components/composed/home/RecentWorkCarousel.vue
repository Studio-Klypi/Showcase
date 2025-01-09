<script setup lang="ts">
import type { HTMLAttributes } from "vue";
import Autoplay from "embla-carousel-autoplay";
import { cn } from "~/lib/utils";

interface WorkProps {
  class?: HTMLAttributes["class"];
}
const props = defineProps<WorkProps>();

interface Work {
  id: number;
  slug: string;
  thumbnail?: string;
  tags?: string[];
  title: string;
  caption: string;
}
const works: Work[] = [
  {
    id: 1845,
    slug: "du-frigo-a-lassiette",
    title: "Du frigo à l’assiette",
    caption: "Trouve les meilleures recettes des plus grands chefs du monde et construis ton repas avec les ingrédients de ton frigo.",
    tags: [
      "E-Commerce",
      "Développement",
      "Woohoo",
    ],
    thumbnail: "https://images.pexels.com/photos/1279330/pexels-photo-1279330.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
  },
  {
    id: 1846,
    slug: "le-tour-du-monde-en-saveurs",
    title: "Le tour du monde en saveurs",
    caption: "Explore des recettes authentiques et savoureuses de différents pays pour voyager depuis ta cuisine.",
    tags: [
      "Cuisine",
      "Voyage",
      "Inspiration",
    ],
    thumbnail: "https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
  },
  {
    id: 1847,
    slug: "astuces-rapides-en-cuisine",
    title: "Astuces rapides en cuisine",
    caption: "Découvre des techniques simples pour cuisiner plus rapidement tout en obtenant des résultats savoureux.",
    tags: [
      "Tips",
      "Rapide",
      "Cuisine",
    ],
    thumbnail: "https://images.pexels.com/photos/958545/pexels-photo-958545.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
  },
  {
    id: 1848,
    slug: "desserts-faciles",
    title: "Desserts faciles",
    caption: "Réalise des desserts gourmands en toute simplicité pour impressionner tes proches.",
    tags: [
      "Desserts",
      "Facile",
      "Gourmandise",
    ],
    thumbnail: "https://images.pexels.com/photos/1640772/pexels-photo-1640772.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
  },
  {
    id: 1849,
    slug: "vegetarien-et-savoureux",
    title: "Végétarien et savoureux",
    caption: "Transforme tes repas végétariens avec des recettes originales et riches en saveurs.",
    tags: [
      "Végétarien",
      "Santé",
      "Saveur",
    ],
    thumbnail: "https://images.pexels.com/photos/1640776/pexels-photo-1640776.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
  },
  {
    id: 1850,
    slug: "cuisiner-avec-les-enfants",
    title: "Cuisiner avec les enfants",
    caption: "Partage des moments complices en cuisine avec des recettes adaptées aux petits chefs.",
    tags: [
      "Famille",
      "Enfants",
      "Cuisine",
    ],
    thumbnail: "https://images.pexels.com/photos/842571/pexels-photo-842571.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
  },
]; // todo: replace with database data.
</script>

<template>
  <Carousel
    v-slot="{ canScrollNext, canScrollPrev }"
    :class="cn('col-span-4 sm:col-span-6 md:col-span-8 lg:col-start-2 xl:col-start-2 xl:col-span-10', props.class)"
    :plugins="[
      Autoplay({
        delay: 10000,
      }),
    ]"
  >
    <CarouselContent>
      <CarouselItem
        v-for="work in works"
        :key="work.slug"
        class="select-none flex flex-col items-center gap-10"
      >
        <NuxtImg
          :src="work.thumbnail ?? 'https://images.pexels.com/photos/1279330/pexels-photo-1279330.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'"
          class="w-full h-40 sm:h-48 md:h-56 lg:h-64 xl:h-80 object-cover rounded-lg"
        />
        <div class="md:w-3/4 flex flex-col gap-4">
          <div class="flex flex-wrap gap-2">
            <Badge
              v-for="tag in work.tags"
              :key="tag"
              variant="secondary"
            >
              {{ tag }}
            </Badge>
          </div>

          <h3 class="text-4xl font-extrabold">
            {{ work.title }}
          </h3>
          <p class="leading-relaxed text-muted-foreground line-clamp-3">
            {{ work.caption }}
          </p>

          <Button class="mt-4 self-start">
            En Savoir Plus
          </Button>
        </div>
      </CarouselItem>
    </CarouselContent>
    <CarouselPrevious
      class="hidden md:grid"
      :disabled="!canScrollPrev"
    />
    <CarouselNext
      class="hidden md:grid"
      :disabled="!canScrollNext"
    />
  </Carousel>
</template>
