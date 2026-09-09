<template>
  <v-app>
    <v-main>
      <TopMenu @section-changed="handleSectionChanged" />
      <HeroSlideTransition />

      <div ref="sectionAnchor">
        <component :is="section[activeComponent]" v-if="activeComponent" />
      </div>

      <v-btn
        class="m-2"
        icon="mdi-theme-light-dark"
        location="top right"
        position="absolute"
        @click="$vuetify.theme.cycle()"
      />
    </v-main>
  </v-app>
</template>

<script lang="ts" setup>
import { ref, nextTick } from "vue";
import HeroSlideTransition from "@/components/HeroSlideTransition.vue";
import TopMenu from "@/components/TopMenu.vue";
import About from "@/components/About.vue";
import Booking from "@/components/Booking.vue";
import Coaching from "@/components/Coaching.vue";
import Reviews from "@/components/Reviews.vue";

type SectionKey = keyof typeof section;

const activeComponent = ref<SectionKey | "">("");
const sectionAnchor = ref<HTMLElement | null>(null);

function handleSectionChanged(newSection: SectionKey) {
  activeComponent.value = newSection;
  nextTick(() => {
    sectionAnchor.value?.scrollIntoView({ behavior: "smooth", block: "start" });
  });
}

const section = {
  About,
  Booking,
  Coaching,
  Reviews,
};
</script>
