<template>
  <section class="card">
    <div class="card-header">
      <h3>Conversor de temperatura</h3>
    </div>

    <hr>

    <div class="card-body">
      <div class="mb-3">
        <label for="temperaturaCelsius" class="form-label">
          Ingrese temperatura en °C:
        </label>
        <input 
          type="number" 
          id="temperaturaCelsius"
          class="form-control" 
          v-model.number="temperaturaCelsius"
          placeholder="Ingrese una temperatura"
        >
      </div>

      <div class="mb-3">
        <p :style="colorTemperatura ? { color: colorTemperatura } : {}">
          Conv temperatura a °F: {{ temperaturaFarenheit.toFixed(2) }}
        </p>
      </div>

      <div class="mb-3">
        <p :style="colorTemperatura ? { color: colorTemperatura } : {}">
          Conv temperatura a K: {{ temperaturaKelvin.toFixed(2) }}
        </p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ConversorTemperatura',

  data() {
    return {
      temperaturaCelsius: null
    };
  },

  computed: {
    temperaturaFarenheit() {
      if (this.temperaturaCelsius === null || this.temperaturaCelsius === undefined || isNaN(this.temperaturaCelsius)) {
        return 0;
      }
      return (this.temperaturaCelsius * 9/5) + 32;
    },

    temperaturaKelvin() {
      if (this.temperaturaCelsius === null || this.temperaturaCelsius === undefined || isNaN(this.temperaturaCelsius)) {
        return 0;
      }
      return this.temperaturaCelsius + 273.15;
    },

    colorTemperatura() {
      if (this.temperaturaCelsius === null || this.temperaturaCelsius === undefined || isNaN(this.temperaturaCelsius)) {
        return null;
      }

      if (this.temperaturaCelsius <= 0) {
        return 'blue';
      } else if (this.temperaturaCelsius > 0 && this.temperaturaCelsius < 15) {
        return 'magenta';
      } else {
        return 'red';
      }
    }
  }
};
</script>

<style scoped>
.card-header {
  background-color: grey;
  color: white;
}
</style>

