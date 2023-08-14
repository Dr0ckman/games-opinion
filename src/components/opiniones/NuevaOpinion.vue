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
        <!-- Itera listaOpiniones e inserta componentes de forma dinámica -->
        <div id="accordion-zone" class="mt-5">
            <div v-for="(opinion, index) in listaOpiniones">
                <div>
                    <AcordeonOpinion :title="opinion.title" :content="opinion.content + ' (Index: ' + String(index) + ')'"
                        :index="index"></AcordeonOpinion>
                    <div class="mt-2">
                        <button class="btn btn-danger me-4" @click="eliminarOpinion(index)">Eliminar</button>
                        <button class="btn btn-warning">Editar</button>
                    </div>
                </div>

            </div>
        </div>
        <div class="mt-5">
            <div class="alert alert-warning" role="alert" v-show="!hideAlert">
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
            hideAlert: false,
        }

    },
    methods: {
        agregarOpinion() { // Agrega una opinión a listaOpiniones
            let opinionTitle = document.querySelector("#name").value
            let opinionContent = document.querySelector("#opinion").value

            if (opinionTitle !== '' && opinionContent !== '') {
                this.listaOpiniones.push({ title: opinionTitle, content: opinionContent })
            }
            else {
                alert("Favor completar los campos requeridos")
            }

            document.querySelector("#name").value = ''
            document.querySelector("#opinion").value = ''
        },
        eliminarOpinion(index) {
            this.listaOpiniones.splice(index, 1)
            console.log(this.listaOpiniones)
        }
    },
    beforeUpdate() {
        console.log(this.listaOpiniones)
        if (this.listaOpiniones.length !== 0) {
            this.hideAlert = true
        }
        else {
            this.hideAlert = false
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
  