<template>
  <div class="hello">
    <ul>
      <li :key={index} v-for="(data, index) in crimeData">
        <CrimeListCard :crimeData="data" />
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { CrimeData } from "@/components/ICrimeList";
import CrimeListCard from '@/components/CrimeListCard';

export default defineComponent({
  name: 'CrimeList',
  data() {
    return {
      crimeData: [] as Array<CrimeData>
    }
  },
  components: {
    CrimeListCard
  },
  methods: {
    fetchData<T>(url: string) : Promise<T> {
      return fetch(url)
          .then(response => {
            if (!response.ok) {
              throw new Error(response.statusText)
            }
            return response.json()
          })
    },
  },
  created() {
    this.fetchData('https://data.police.uk/api/crimes-street/all-crime?poly=52.268,0.543:52.794,0.238:52.130,0.478&date=2022-04')
        .then(data => {
          this.crimeData = data as Array<CrimeData>;
          console.log(data);
        })
  }
});
</script>

<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>