<script setup lang="ts">
import MenuLink from "~/components/layout/navigation/MenuLink.vue";

const { t } = useI18n();
</script>

<template>
  <MenuLink to="/studio">
    {{ t("navigation.links.studio") }}
  </MenuLink>
  <MenuLink to="/work">
    {{ t("navigation.links.work") }}
  </MenuLink>
  <MenuLink to="/edito">
    {{ t("navigation.links.edito") }}
  </MenuLink>
  <MenuLink to="/team">
    {{ t("navigation.links.team") }}
  </MenuLink>
</template>
