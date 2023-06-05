<script setup>
  import MainSection from './components/MainSection.vue'
</script>

<template>
  <header>
    <nav class="nav">
      <div>
        <img src="./assets/images/logo.png" alt="logo da página" />
      </div>
    </nav>
    <div class="banner">
      <div class="banner--text">
        <h1 class="banner--text-h1">Conheça o Covidômetro</h1>
        <p class="banner--text-p">Fique atualizado com velocidade e transparência. O covidômetro é uma ferramenta que mostra para você em tempo real o número de casos e óbitos relacionados a pandemia da COVID-19 ao redor do mundo</p>
      </div>
      <div class="banner--image">
        <img src="./assets/images/doctors.svg" alt="figura doutoras" />
      </div>
    </div>
  </header>

  <main>
    <MainSection />
  </main>
</template>

<style scoped>
.nav {
  background-color: #fff;
  height: 4rem;
  display: flex;
  justify-content: center;
  align-items: center;
  box-shadow: 0px 15px 10px -15px rgb(207, 207, 207);
}

.banner {
  margin: 1rem;
  display: flex
}

.banner--image {
  display: none;
}

@media (min-width: 815px) {
  .nav {
    padding-left: 8rem;
    justify-content: space-between;
  }

  .banner {
    margin: 3rem 8rem;
    justify-content: space-between;
  }

  .banner--text {
    margin: 4rem 1.5rem 0 0;
    max-width: 45rem;
  }

  .banner--text-h1 {
    font-size: 2.5rem;
  }
  .banner--text-p {
    font-size: 1.2rem;
  }

  .banner--image {
    display: block;
  }
}
</style>
