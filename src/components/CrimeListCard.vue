<template>
  <v-card
    class="cw__card mx-auto"
    max-width="344"
    elevation="10"
  >
    <v-list-item three-line>
      <v-list-item-content>
        <div class="text-overline mb-4">
          DATE: {{ crimeData.month }}
        </div>
        <v-list-item-title class="text-h5 mb-1">
          Crime: {{ crimeData.category }}
        </v-list-item-title>
        <v-list-item-subtitle>{{ crimeData.location.street.name }}</v-list-item-subtitle>
      </v-list-item-content>

      <v-list-item-avatar
        src="https://cdn.vuetifyjs.com/images/john.jpg"
        alt="john"
      ></v-list-item-avatar>
    </v-list-item>
  </v-card>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { CrimeData } from "@/components/ICrimeList";

export default defineComponent({
  name: 'CrimeListCard',
  data() {
    return {

    }
  },
  props: {
    crimeData: Object
  },
  methods: {

  }
});
</script>

<style scoped lang="scss">

.cw {
    &__card {
        margin: 10px 6px;
    }
} 

</style>