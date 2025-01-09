<script setup lang="ts">
import type { HTMLAttributes } from "vue";
import { Smartphone, Mail, MapPin } from "lucide-vue-next";
import { cn } from "~/lib/utils";
import SectionContent from "~/components/composing/page/SectionContent.vue";
import LargeHorizontalLogo from "~/components/branding/LargeHorizontalLogo.vue";
import ActionLink from "~/components/layout/footer/ActionLink.vue";
import ExternalLink from "~/components/layout/footer/ExternalLink.vue";
import FooterSection from "~/components/layout/footer/section/FooterSection.vue";
import FooterSectionLabel from "~/components/layout/footer/section/FooterSectionLabel.vue";
import LocalLink from "~/components/layout/footer/LocalLink.vue";

interface FooterProps {
  class?: HTMLAttributes["class"];
}
const props = defineProps<FooterProps>();
const { t } = useI18n();
</script>

<template>
  <footer :class="cn('px-8', props.class)">
    <SectionContent class="py-20">
      <!-- brand -->
      <div class="col-span-4 sm:col-span-6 md:col-span-4 flex flex-col items-start gap-3">
        <LargeHorizontalLogo class="h-12 mb-7" />

        <ActionLink to="tel:+33388315386">
          <Smartphone />
          <span>{{ t("layout.footer.phoneNumber") }}</span>
        </ActionLink>
        <ActionLink to="mailto:contact@studio-klypi.com">
          <Mail />
          <span>contact@studio-klypi.com</span>
        </ActionLink>
        <ExternalLink to="https://maps.app.goo.gl/ws3fWXXfcHKYDSA27">
          <MapPin />
          <span v-html="t('layout.footer.postalAddress')" />
        </ExternalLink>
      </div>

      <FooterSection class="mt-12 sm:mt-0 col-span-4 sm:col-span-2 xl:col-start-7">
        <FooterSectionLabel>{{ t("layout.footer.texts.label") }}</FooterSectionLabel>
        <LocalLink to="/legal/mentions">
          {{ t("layout.footer.texts.legalMentions") }}
        </LocalLink>
        <LocalLink to="/legal/cgv">
          {{ t("layout.footer.texts.sellConditions") }}
        </LocalLink>
      </FooterSection>
      <FooterSection class="col-span-4 sm:col-span-2">
        <FooterSectionLabel>{{ t("layout.footer.utils.label") }}</FooterSectionLabel>
        <LocalLink to="/help">
          {{ t("layout.footer.utils.help") }}
        </LocalLink>
        <ExternalLink to="https://www.instagram.com/uiux.loicmaes">
          {{ t("layout.footer.utils.instagram") }}
        </ExternalLink>
        <ExternalLink to="https://www.threads.net/uiux.loicmaes">
          {{ t("layout.footer.utils.threads") }}
        </ExternalLink>
        <ExternalLink to="https://www.github.com/studio-klypi">
          {{ t("layout.footer.utils.github") }}
        </ExternalLink>
      </FooterSection>
      <FooterSection class="col-span-4 sm:col-span-2 md:col-start-5 xl:col-start-auto">
        <FooterSectionLabel>{{ t("layout.footer.products.label") }}</FooterSectionLabel>
        <p class="italic text-sm text-muted-foreground">
          {{ t("layout.footer.products.noProducts") }}
        </p>
      </FooterSection>

      <div class="mt-12 flex flex-col sm:flex-row sm:justify-between col-span-4 sm:col-span-6 md:col-span-8 lg:col-span-10 xl:col-span-12">
        <p>{{ t("layout.footer.rights") }}</p>
        <p>{{ t("layout.footer.author") }}</p>
      </div>
    </SectionContent>
  </footer>
</template>
