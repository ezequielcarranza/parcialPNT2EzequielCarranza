<template>
  <div class="container-fluid mt-3">
    <div class="card">
      <div class="card-header">
        <header>
          <h2>Parcial - Ezequiel Carranza</h2>
        </header>
      </div>

      <hr>

      <div class="card-body">
        <main>
          <Navbar />

          <RouterView />
        </main>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';

export default {
  name: 'App',
  components: {
    Navbar
  }
}
</script>

<style scoped>
.card-header {
  background-color: red;
  color: white;
}
</style>
