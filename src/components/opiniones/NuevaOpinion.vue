<template>
    <div class="container-fluid">
    <h3>Escribe tu opinión para el juego {{ $route.params.juego }}</h3>
    <form>
        <label for="name" class="form-label">Nombre</label>
        <input type="text" id="name" class="form-control">
        <br>
        <label for="opinion" class="form-label">Opinión</label>
        <textarea id="opinion" rows="5" class="form-control input-opinion"></textarea>
        <br>
        <input type="button" class="btn btn-primary" value="Agregar">
    </form>

    <br />
    <Opinion title="Opinión creada por (( autor ))" content="Contenido de la opinión" />
</div>
</template>
  
<script>

import Opinion from './Opinion.vue'

export default {
    name: 'NuevaOpinion',
    components: {
        Opinion
    }
}
</script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .form-control {
        max-width: 20rem;
    }
</style>
  