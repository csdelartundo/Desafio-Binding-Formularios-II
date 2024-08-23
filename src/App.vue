<template>
  <div id="app" class="container my-5">
    <div class="row justify-content-center">

      <div class="col-md-4 bg-dark text-light p-4 rounded">
        <h4 class="mb-3">Título</h4>
        <input v-model="titulo" class="form-control mb-3" placeholder="Ingresa el título">

        <h4 class="mb-3">Emoji</h4>
        <select v-model="emoji" class="form-select mb-3">
          <option :value="emojiM">{{ emojiM }}</option>
          <option :value="emojiF">{{ emojiF }}</option>
        </select>

        <h4 class="mb-3">Apreciación</h4>
        <div class="form-check">
          <input type="radio" id="regular" value="Regular" v-model="apreciacion" class="form-check-input">
          <label for="regular" class="form-check-label">Regular</label>
        </div>
        <div class="form-check">
          <input type="radio" id="bien" value="Bien" v-model="apreciacion" class="form-check-input">
          <label for="bien" class="form-check-label">Bien</label>
        </div>
        <div class="form-check">
          <input type="radio" id="muyBien" value="Muy Bien" v-model="apreciacion" class="form-check-input">
          <label for="muyBien" class="form-check-label">Muy Bien</label>
        </div>
        <div class="form-check">
          <input type="radio" id="increible" value="Increíble" v-model="apreciacion" class="form-check-input">
          <label for="increible" class="form-check-label">Increíble</label>
        </div>

        <h4 class="mb-3 mt-4">Competencias Aprendidas</h4>
        <div class="form-check">
          <input type="checkbox" id="competencia1" value="Morfología de un componente" v-model="competencias"
            class="form-check-input">
          <label for="competencia1" class="form-check-label">Morfología de un componente</label>
        </div>
        <div class="form-check">
          <input type="checkbox" id="competencia2" value="One-Way y Two-Way Data Binding" v-model="competencias"
            class="form-check-input">
          <label for="competencia2" class="form-check-label">One-Way y Two-Way Data Binding</label>
        </div>
        <div class="form-check">
          <input type="checkbox" id="competencia3" value="El patrón de diseño MVVM" v-model="competencias"
            class="form-check-input">
          <label for="competencia3" class="form-check-label">El patrón de diseño MVVM</label>
        </div>
        <div class="form-check">
          <input type="checkbox" id="competencia4" value="Directivas" v-model="competencias" class="form-check-input">
          <label for="competencia4" class="form-check-label">Directivas</label>
        </div>
        <div class="form-check">
          <input type="checkbox" id="competencia5" value="Estado" v-model="competencias" class="form-check-input">
          <label for="competencia5" class="form-check-label">Estado</label>
        </div>

        <h4 class="mb-3 mt-4">Opinión</h4>
        <textarea v-model="opinion" class="form-control" placeholder="Escribe tu opinión aquí..."></textarea>
      </div>

      <div class="col-md-6 bg-light text-dark p-4 rounded ms-4">
        <div class="text-center">
          <h1>{{ emoji }}</h1>
          <h2>{{ titulo }}</h2>
          <h3>Y me parece {{ apreciacion }}</h3>
          <h4>He aprendido:</h4>
          <ul>
            <li v-for="competencia in competencias" :key="competencia">{{ competencia }}</li>
          </ul>
          <h4>Mi opinión hasta ahora del framework es:</h4>
          <p>{{ opinion }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      titulo: "",
      emoji: "",
      emojiM: "👨🏻‍💻",
      emojiF: "👩🏻‍💻",
      apreciacion: "",
      competencias: [],
      opinion: "",
    };
  }
};
</script>

<style scoped>
#app {
  max-width: 1200px;
  margin: auto;
}

</style>
