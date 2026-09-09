<template>
  <v-app-bar color="white" dense flat>
    <v-container class="py-0 fill-height">
      <v-row align="center">
        <v-col cols="12" class="text-center">
          <v-btn color="primary" class="mr-2 pl-4" @click="showAbout">
            About
          </v-btn>
          <v-btn color="primary" class="mr-2 pl-4" @click="showCoaching">
            Coaching
          </v-btn>
          <v-btn color="primary" class="mr-2 pl-4" @click="showBooking">
            Booking
          </v-btn>
          <v-btn color="primary" class="mr-2 pl-4" @click="showReviews">
            Reviews
          </v-btn>
        </v-col>
      </v-row>
    </v-container>
  </v-app-bar>
</template>

<script lang="ts">
import { defineEmits } from "vue";

export default {
  emits: ["section-changed"],

  methods: {
    showAbout() {
      this.$emit("section-changed", "About");
    },

    showCoaching() {
      this.$emit("section-changed", "Coaching");
    },

    showBooking() {
      this.$emit("section-changed", "Booking");
    },

    showReviews() {
      this.$emit("section-changed", "Reviews");
    },
  },
};
</script>
