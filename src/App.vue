<template>
  <v-app>
    <v-main>
      <TopMenu /><!--:slots="['About', 'Booking', 'Q+A', 'Reviews']" -->
      <HeroSlideTransition />
      <!-- <HelloWorld /> -->
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
import HeroSlideTransition from "@/components/HeroSlideTransition.vue";
import TopMenu from "@/components/TopMenu.vue";
// import HelloWorld from "@/components/HelloWorld.vue";
</script>
