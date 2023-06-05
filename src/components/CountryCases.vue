<script setup>
import { computed } from "vue"

const props = defineProps({
  country: Object
})

const getFatality = computed(function() {
  const fatalityRate = (props.country.deceased * 100) / props.country.infected
  return `${fatalityRate.toFixed(2)}%`
})
</script>

<template>
  <div class="div-country">
    <h2>{{props.country.country}}</h2>
    <div class="div-cases">
      <div class="div-case-item">
        <div class="case-title">Total de casos</div>
        <div class="case-value">{{props.country.infected || '-'}}</div>
      </div>
      <div class="div-case-item">
        <div class="case-title">Mortes</div>
        <div class="case-value">{{props.country.deceased || '-'}}</div>
      </div>
      <div class="div-case-item">
        <div class="case-title">Fatalidade</div>
        <div class="case-value">{{getFatality}}</div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.div-country{
  border: 1px solid #e2e2e2;
  border-radius: 5px;
  margin: 0 1rem;
  text-align: center;
  background-color: #FFF;
}

.div-cases {
  margin-bottom: 1.5rem;
}

.case-title {
  margin-top: 1rem;
}

.case-value {
  color: #ef6261;
  font-size: 1.5rem;
}

@media (min-width: 815px) {
  .div-country {
    margin: 0 15rem;
  }

  .div-cases {
    display: flex;
    justify-content: space-between;
  }
}

@media (min-width: 1145px) {
  .div-cases {
    display: flex;
    justify-content: space-between;
    padding: 0 10rem;
  }
}

</style>
