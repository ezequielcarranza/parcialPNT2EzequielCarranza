<template>
  <section class="card">
    <div class="card-header">
      <h3>Respuestas al multple choice</h3>
    </div>

    <div class="card-body mt-4">
      <table class="table table-bordered">
            <thead>
              <tr>
                <th>Pregunta Nro.</th>
                <th>Respuesta</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(respuesta, index) in respuestas" :key="index">
                <td>{{ index + 1 }}</td>
                <td>{{ respuesta }}</td>
              </tr>
            </tbody>
          </table>

    </div>
  </section>
</template>

<script>
export default {
  name: 'Respuestas',

  data() {
    return {
      respuestas: ['c', 'c', 'a']
    };
  }
};
</script>

<style scoped>
.card-header {
  background-color: blue;
  color: white;
}

.table td,
.table th {
  text-align: center;
  vertical-align: middle;
}
</style>

