<script setup>
import CountryFilter from './CountryFilter.vue'
import CountryCases from './CountryCases.vue'
import { computed, onBeforeMount, ref } from 'vue'

let countries = ref([])
const filter = ref("");

onBeforeMount(async () => {
  const response = await fetch(
    'https://api.apify.com/v2/key-value-stores/tVaYRsPHLjNdNBu7S/records/LATEST?disableRedirect=true'
  )
    .then((response) => response.json())
    .then((result) => result)
    .catch((error) => console.log('error', error))

  countries.value = response
})

const getCoutriesList = computed(function() {
  const countriesList = countries.value.filter((item) => item.country.toLowerCase().includes(filter.value))
  console.log
  return countriesList
})
</script>

<template>
  <CountryFilter class="filter" v-model="filter" />
  <CountryCases v-for="(country, idx) in getCoutriesList" :key="idx" class="country" :country="country" />
</template>

<style scoped>
.filter {
  margin-bottom: 2rem;
}

.country {
  margin-bottom: 1rem;
}
</style>
