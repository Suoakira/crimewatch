<template>
  <v-container>
    <CrimeList msg="Welcome to Your Vue.js + TypeScript App"/>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue';
import CrimeList from '@/components/CrimeList.vue'; // @ is an alias to /src

export default Vue.extend({
  name: 'HomeView',
  components: {
    CrimeList,
  },
});
</script>

<style lang="scss" scoped>
</style>