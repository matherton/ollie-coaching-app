<script setup>
import { shallowRef } from "vue";

const value = shallowRef(new Date().toISOString().split("T")[0]);
</script>
<template>
  <div class="text-center p-4">
    <h1>Book Coaching Sessions</h1>

    <v-layout>
      <v-container>
        <v-fab
          icon="mdi-refresh"
          location="top end"
          app
          v-tooltip="'Clear selection'"
          @click="value = null"
        ></v-fab>

        <div class="d-flex flex-wrap justify-space-around ga-6">
          <v-date-picker
            v-model="value"
            color="purple"
            header-date-format="monthAndDate"
            landscape-header-width="250"
            landscape
            :min="new Date().toISOString().split('T')[0]"
          ></v-date-picker>
        </div>
      </v-container>
    </v-layout>
  </div>
</template>
<style scoped></style>
