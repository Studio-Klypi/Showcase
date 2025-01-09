<script setup lang="ts">
import type { HTMLAttributes } from "vue";
import { Star } from "lucide-vue-next";
import { cn } from "~/lib/utils";

interface TestimonialProps {
  avatarUri?: string;
  author: {
    name: string;
    job: string;
  };
  content: string;
  note: number;
  class?: HTMLAttributes["class"];
}
const props = defineProps<TestimonialProps>();
</script>

<template>
  <Card :class="cn('select-none cursor-pointer col-span-4 sm:col-span-3 sm:row-span-2 md:col-span-4 lg:col-span-3 xl:col-span-4 transition-all duration-300 ease-in-out hover:scale-105 hover:shadow-2xl', props.class)">
    <CardHeader class="flex flex-row items-center gap-3">
      <Avatar
        shape="square"
        size="md"
      >
        <AvatarImage
          v-if="props.avatarUri"
          :src="props.avatarUri"
        />
        <AvatarFallback>{{ props.author.name.substring(0, 2).toUpperCase() }}</AvatarFallback>
      </Avatar>

      <div class="flex-1 flex flex-col">
        <p class="text-lg font-bold leading-none">
          {{ props.author.name }}
        </p>
        <span class="text-sm text-muted-foreground">{{ props.author.job }}</span>
      </div>

      <div class="flex items-center gap-2">
        <span class="font-medium">{{ props.note }}</span>
        <Star class="h-4 w-4" />
      </div>
    </CardHeader>
    <CardContent>
      <p class="text-pretty leading-relaxed line-clamp-6">
        {{ props.content }}
      </p>
    </CardContent>
  </Card>
</template>
