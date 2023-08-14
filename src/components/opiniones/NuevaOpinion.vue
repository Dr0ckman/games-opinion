<template>
    <div class="container-fluid">
        <h3>Escribe tu opinión para el juego {{ $route.params.juego }}</h3> <!-- Toma el nombre del juego de la URL -->
        <form>
            <label for="name" class="form-label">Nombre</label>
            <input type="text" id="name" class="form-control">
            <br>
            <label for="opinion" class="form-label">Opinión</label>
            <textarea id="opinion" rows="5" class="form-control input-opinion"></textarea>
            <br>
            <input type="button" id="btn-agregar" class="btn btn-primary" value="Agregar" @click="agregarOpinion()">
        </form>
        <div id="accordion-zone" class="mt-5" v-for="opinion in listaOpiniones"> <!-- Itera listaOpiniones e inserta componentes de forma dinámica -->
            <AcordeonOpinion :title="opinion.title" :content="opinion.content"></AcordeonOpinion>
        </div>
        <div class="mt-5">
            <div class="alert alert-warning" role="alert" v-show="visible">
                <strong>No hay opiniones disponibles</strong>
            </div>
        </div>
    </div>
</template>
  
<script>

import AcordeonOpinion from './AcordeonOpinion.vue'

export default {
    name: 'NuevaOpinion',
    components: {
        AcordeonOpinion
    },
    data() {
        return {
            listaOpiniones: [],
            visible: true
        }

    },
    methods: {
        agregarOpinion() { // Agrega una opinión a listaOpiniones
            let opinionTitle = document.querySelector("#name").value
            let opinionContent = document.querySelector("#opinion").value

            if (opinionTitle !== '' && opinionContent !== '') {
                this.listaOpiniones.push({ title: opinionTitle, content: opinionContent })
                this.visible = false
            }
            else {
                alert("Favor completar los campos requeridos")
            }
        }
    }
}



</script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.form-control {
    max-width: 20rem;
}
</style>
  